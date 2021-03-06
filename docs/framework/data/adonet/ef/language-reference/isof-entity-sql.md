---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 87d69f58fc0c45eacb4ee63997129347f7f2a857
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827403"
---
# <a name="isof-entity-sql"></a>ISOF (Entity SQL)
Determina se o tipo de uma expressão é do tipo especificado ou um de seus subtipos.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Qualquer expressão de consulta válida para determinar o tipo de.  
  
 NOT  
 Nega o resultado de EDM.Boolean de ESTÁ DE.  
  
 SOMENTE  
 Especifica que É returns `true` somente se `expression` é do tipo `type` e não qualquer um de seus subtipos.  
  
 `type`  
 O tipo para testar `expression` contra. O tipo URL deve ser qualificada.  
  
## <a name="return-value"></a>Valor de retorno  
 `true` se `expression` é do tipo T e T é um tipo base, ou um tipo derivado de `type`; se `expression` nulo é nulo em tempo de execução; caso contrário, `false`.  
  
## <a name="remarks"></a>Comentários  
 As expressões `expression IS NOT OF (type)` e `expression IS NOT OF (ONLY type)` são sintaticamente equivalentes à `NOT (expression IS OF (type))` e `NOT (expression IS OF (ONLY type))`, respectivamente.  
  
 A tabela a seguir mostra o comportamento do operador de `IS OF` sobre alguns padrões e típicos do canto. Todas as exceções são geradas do lado do cliente antes que o provedor obtenha chamado:  
  
|Padrão|Comportamento|  
|-------------|--------------|  
|o zero ESTÁ DE (EntityType)|Gera|  
|o zero ESTÁ DE (ComplexType)|Gera|  
|o zero ESTÁ DE (RowType)|Gera|  
|O DELEITE (zero) COMO EntityType ESTÁ DE (EntityType)|Retorna DBNull|  
|O DELEITE (zero) COMO ComplexType ESTÁ DE (ComplexType)|Gera|  
|O DELEITE (zero) COMO RowType ESTÁ DE (RowType)|Gera|  
|EntityType ESTÁ DE (EntityType)|Retorna retificam/falso|  
|ComplexType ESTÁ DE (ComplexType)|Gera|  
|RowType ESTÁ DE (RowType)|Gera|  
  
## <a name="example"></a>Exemplo  
 O seguinte [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta usa é de operador para determinar o tipo de uma expressão de consulta e, em seguida, usa o operador de DELEITE para converter um objeto do tipo de curso em uma coleção de objetos do tipo OnsiteCourse. A consulta se baseia a [modelo de escola](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>Consulte também
- [Referência de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
