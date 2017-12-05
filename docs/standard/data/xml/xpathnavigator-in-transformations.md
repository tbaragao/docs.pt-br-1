---
title: "XPathNavigator nas transformações"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09f89708607ada18181bc6605994c7908e1dd14b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="91e32-102">XPathNavigator nas transformações</span><span class="sxs-lookup"><span data-stu-id="91e32-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="91e32-103">A classe de <xref:System.Xml.XPath.XPathNavigator> fornece de acesso aleatório somente leitura a dados e é criada para uso como uma entrada ao idioma extensível de folha de estilos para transformações (XSLT).</span><span class="sxs-lookup"><span data-stu-id="91e32-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="91e32-104">É implementada em <xref:System.Xml.XPath.XPathDocument>, em <xref:System.Xml.XmlDataDocument>, e em <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="91e32-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="91e32-105"><xref:System.Xml.XPath.XPathNavigator> é baseado no modelo de dados do World Wide Web Consortium (W3C) como descrito na seção 5 de recomendação de idioma do caminho de XML (XPath).</span><span class="sxs-lookup"><span data-stu-id="91e32-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="91e32-106"><xref:System.Xml.XPath.XPathNavigator> define um modelo de cursor sobre qualquer armazenamento e fornece consultas XPath rápidas, somente leitura sobre qualquer armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="91e32-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="91e32-107"><xref:System.Xml.XPath.XPathNavigator> também é a classe usar para iterar sobre partes da árvore de resultado.</span><span class="sxs-lookup"><span data-stu-id="91e32-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="91e32-108">API permite que você obtenha informações do nó atual no armazenamento e para mover a nós conectados.</span><span class="sxs-lookup"><span data-stu-id="91e32-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="91e32-109">O <xref:System.Xml.XPath.XPathNavigator> é um modelo de estilo de cursor que executa a passagem por um repositório usando um conjunto de **mover** métodos.</span><span class="sxs-lookup"><span data-stu-id="91e32-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="91e32-110"><xref:System.Xml.XPath.XPathNavigator> sempre é posicionado em um nó.</span><span class="sxs-lookup"><span data-stu-id="91e32-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="91e32-111">Qualquer **mover** método falha deixa o <xref:System.Xml.XPath.XPathNavigator> inalterado.</span><span class="sxs-lookup"><span data-stu-id="91e32-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="91e32-112"><xref:System.Xml.XPath.XPathNavigator> é a classe usar para iterar sobre partes da árvore de resultado.</span><span class="sxs-lookup"><span data-stu-id="91e32-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="91e32-113">O exemplo de código a seguir cria um fragmento da árvore de resultado em uma folha de estilos chamar a função com o parâmetro, `fragment`, que contém XML.</span><span class="sxs-lookup"><span data-stu-id="91e32-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="91e32-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="91e32-114">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl ="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
  
<xsl:variable name="fragment">  
    <authorlist>  
       <author>Joe</author>  
    </authorlist>  
</xsl:variable>  
  
<msxsl:script language="C#" implements-prefix="user">  
<![CDATA[  
   string NodeFragment(XPathNavigator nav)  
   {  
      if (nav.HasChildren)  
        return nav.Value;  
      else  
        return "";  
   }  
]]>  
</msxsl:script>  
  
<xsl:template match="/">  
     <xsl:value-of select="user:NodeFragment($fragment)"/>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="91e32-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="91e32-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="91e32-116">O código a seguir usa o **test.xsl** folha de estilo e **test.xml** dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="91e32-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
Public Class sample  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load("test.xsl")  
  
        Dim xd As New XPathDocument("test.xml")  
  
        Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
        xslt.Transform(xd, Nothing, strmTemp, Nothing)  
    End Sub 'Main  
End Class 'sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, null, strmTemp, null);  
    }  
}  
```  
  
## <a name="output"></a><span data-ttu-id="91e32-117">Saída</span><span class="sxs-lookup"><span data-stu-id="91e32-117">Output</span></span>  
 <span data-ttu-id="91e32-118">O resultado da transformação foi encontrado no arquivo **out.xml**:</span><span class="sxs-lookup"><span data-stu-id="91e32-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="91e32-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="91e32-119">See Also</span></span>  
 [<span data-ttu-id="91e32-120">Classe XslTransform implementa do processador XSLT</span><span class="sxs-lookup"><span data-stu-id="91e32-120">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)