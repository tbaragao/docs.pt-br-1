---
title: '#Diretiva ExternalSource (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: 550934723a5599573be578ce5746ab7520b59dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705963"
---
# <a name="externalsource-directive"></a>Diretiva #ExternalSource
Indica um mapeamento entre linhas específicas do código-fonte e texto externo à origem.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Partes  
 `StringLiteral`  
 O caminho para a fonte externa.  
  
 `IntLiteral`  
 O número de linha da primeira linha da fonte externa.  
  
 `LogicalLine`  
 A linha onde o erro ocorre na fonte externa.  
  
 `#End ExternalSource`  
 Encerra o `#ExternalSource` bloco.  
  
## <a name="remarks"></a>Comentários  
 Essa diretiva é usada apenas pelo compilador e o depurador.  
  
 Um arquivo de origem pode incluir diretivas de fonte externa, que indicam um mapeamento entre linhas específicas do código no arquivo de origem e o texto externo à origem, como um arquivo. aspx. Se forem encontrados erros no código-fonte designado durante a compilação, eles são identificados como proveniente da fonte externa.  
  
 Diretivas de fonte externa não têm nenhum efeito na compilação e não podem ser aninhadas. Eles são destinados a uso interno por apenas o aplicativo.  
  
## <a name="see-also"></a>Consulte também
- [Compilação Condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
