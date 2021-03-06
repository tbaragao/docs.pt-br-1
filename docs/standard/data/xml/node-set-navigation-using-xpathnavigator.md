---
title: Navegação do nó usando XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58adf0251fdc7427f493e8bf9947c081bfccd2a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618088"
---
# <a name="node-set-navigation-using-xpathnavigator"></a>Navegação do nó usando XPathNavigator
Você pode navegar sobre nós em <xref:System.Xml.XPath.XPathDocument> ou o objeto de <xref:System.Xml.XmlDocument> que usa os métodos definidos de navegação do nó de <xref:System.Xml.XPath.XPathNavigator> classe. Você pode navegar sobre todos os nós ou sobre um conjunto selecionado de nós retornados por um dos métodos de seleção de classe de <xref:System.Xml.XPath.XPathNavigator> .  
  
## <a name="element-node-set-navigation"></a>Navegação do nó de elemento  
 A classe de <xref:System.Xml.XPath.XPathNavigator> fornece vários métodos usados para navegar em nós do elemento. A tabela a seguir mostra os métodos de navegação disponíveis e uma descrição de como se movem; isso não inclui os métodos usados para navegar nós de atributo e de namespace.  
  
 Para saber mais sobre como escolher nós no objeto <xref:System.Xml.XPath.XPathNavigator>, confira [Selecionar, avaliar e corresponder dados XML usando XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md). Para saber mais sobre a navegação de nós de atributo e do namespace, confira [Navegação do nó de atributo e do namespace usando XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
|Método|Descrição|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|Move <xref:System.Xml.XPath.XPathNavigator> a mesma posição de <xref:System.Xml.XPath.XPathNavigator> especificou.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|Move <xref:System.Xml.XPath.XPathNavigator> a um nó filho do nó atual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|Move <xref:System.Xml.XPath.XPathNavigator> ao primeiro nó irmãos do nó atual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|Move <xref:System.Xml.XPath.XPathNavigator> ao primeiro nó filho do nó atual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|Move <xref:System.Xml.XPath.XPathNavigator> ao elemento especificado na ordem de documento.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|Move <xref:System.Xml.XPath.XPathNavigator> o nó que possui um atributo do tipo `ID` com um valor que corresponde <xref:System.String>determinado.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|Move <xref:System.Xml.XPath.XPathNavigator> o nó seguir irmãos do nó atual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|Move <xref:System.Xml.XPath.XPathNavigator> o nó pai do nó atual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|Move <xref:System.Xml.XPath.XPathNavigator> o nó anterior irmãos do nó atual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|Move <xref:System.Xml.XPath.XPathNavigator> ao nó raiz de documento XML.|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a>Comentários e navegação do nó de instrução de processamento  
 Os seguintes métodos da classe <xref:System.Xml.XPath.XPathNavigator> são válidos para mover para comentários ou as instruções de processamento de outros nós em um documento XML.  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Processar dados XML usando o modelo de dados XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Navegação do nó de atributo e de namespace usando o XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [Extrair dados XML usando XPathNavigator](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)
- [Acessando dados XML fortemente tipados usando o XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
