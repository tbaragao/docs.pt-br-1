---
title: Aplicando uma transformação XSLT a um conjunto de dados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: b665fc9593cd73e759625bdfd537581958f8734d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595559"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a>Aplicando uma transformação XSLT a um conjunto de dados
O **WriteXml** método o <xref:System.Data.DataSet> permite que você escreva o conteúdo de um **conjunto de dados** como dados XML. Uma tarefa comum é, em seguida, transformar esse XML em outro formato usando transformações XSL (XSLT). No entanto, sincronizando um **conjunto de dados** com um <xref:System.Xml.XmlDataDocument> permite que você aplique uma folha de estilos XSLT ao conteúdo de uma **conjunto de dados** sem precisar primeiro escrever o conteúdo do  **Conjunto de dados** como dados XML usando **WriteXml**.  
  
 O exemplo a seguir preenche um **DataSet** com tabelas e relações, sincroniza o **DataSet** com um **XmlDataDocument**e grava uma parte do  **Conjunto de dados** como uma marca HTML de arquivos usando uma folha de estilos XSLT. Este é o conteúdo da folha de estilos XSLT.  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 O código a seguir preenche o **conjunto de dados** e aplica-se a folha de estilos XSLT.  
  
> [!NOTE]
>  Se você estiver aplicando uma folha de estilos XSLT a um **conjunto de dados** que contém relações, obter o melhor desempenho se você definir o **Nested** propriedade do <xref:System.Data.DataRelation> para **true**para cada relação de aninhados. Isso permite usar folhas de estilos XSLT que implementam natural de cima para baixo o processamento navegar na hierarquia e transformar os dados, em vez de usar eixos de localização de XPath de alto desempenho (por exemplo, irmão anterior e irmão seguinte no estilo folha nó expressões de teste) para navegar por ele. Para obter mais informações sobre relações aninhadas, consulte [aninhamento de DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);   
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",   
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a>Consulte também
- [Sincronização de DataSet e XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [ADO.NET Managed Providers and DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)
