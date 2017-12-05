---
title: ENTRE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6ab5c08dad5f11d968eec4efa51ff225d3cfd0fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="between-entity-sql"></a><span data-ttu-id="02d47-102">ENTRE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="02d47-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="02d47-103">Determina se uma expressão resulta em um valor em um intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="02d47-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="02d47-104">O [!INCLUDE[esql](../../../../../../includes/esql-md.md)] entre a expressão tem a mesma funcionalidade que a expressão Transact-SQL entre.</span><span class="sxs-lookup"><span data-stu-id="02d47-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d47-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="02d47-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="02d47-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="02d47-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="02d47-107">Qualquer expressão válida para testar no intervalo definido por `begin_expression` e por `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="02d47-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="02d47-108">`expression` deve ser do mesmo tipo de `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="02d47-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="02d47-109">Qualquer expressão válida.</span><span class="sxs-lookup"><span data-stu-id="02d47-109">Any valid expression.</span></span> <span data-ttu-id="02d47-110">`begin_expression` deve ser do mesmo tipo de `expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="02d47-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="02d47-111">`begin_expression` deve ser menor que `end_expression`, o valor de retorno será negado mais.</span><span class="sxs-lookup"><span data-stu-id="02d47-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="02d47-112">Qualquer expressão válida.</span><span class="sxs-lookup"><span data-stu-id="02d47-112">Any valid expression.</span></span> <span data-ttu-id="02d47-113">`end_expression` deve ser do mesmo tipo de `expression` e `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="02d47-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="02d47-114">NOT</span><span class="sxs-lookup"><span data-stu-id="02d47-114">NOT</span></span>  
 <span data-ttu-id="02d47-115">Especifica que o resultado de ENTER é negado.</span><span class="sxs-lookup"><span data-stu-id="02d47-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="02d47-116">AND</span><span class="sxs-lookup"><span data-stu-id="02d47-116">AND</span></span>  
 <span data-ttu-id="02d47-117">Atua como um espaço reservado que indica que `expression` deve estar dentro do intervalo indicado por `begin_expression` e por `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="02d47-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02d47-118">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="02d47-118">Return Value</span></span>  
 <span data-ttu-id="02d47-119">`true` se `expression` está entre o intervalo indicado por `begin_expression` e `end_expression`; caso contrário, `false`.</span><span class="sxs-lookup"><span data-stu-id="02d47-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="02d47-120">`null` será retornado se `expression` é `null` ou se `begin_expression` ou `end_expression` são `null`.</span><span class="sxs-lookup"><span data-stu-id="02d47-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d47-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="02d47-121">Remarks</span></span>  
 <span data-ttu-id="02d47-122">Para especificar um intervalo exclusivo, use o maior que (>) e o menor que (<) operadores em vez de NO MEIO.</span><span class="sxs-lookup"><span data-stu-id="02d47-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02d47-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="02d47-123">Example</span></span>  
 <span data-ttu-id="02d47-124">Os seguintes usos da consulta SQL Entity ENTER o operador determinar se uma expressão resulta em um valor em um intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="02d47-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="02d47-125">A consulta é baseada no modelo de vendas AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="02d47-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="02d47-126">Para compilar e executar essa consulta, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="02d47-126">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="02d47-127">Siga o procedimento [como: executar uma consulta que retorna resultados de StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="02d47-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="02d47-128">Passe a consulta a seguir como um argumento para o método `ExecuteStructuralTypeQuery`:</span><span class="sxs-lookup"><span data-stu-id="02d47-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="02d47-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="02d47-129">See Also</span></span>  
 [<span data-ttu-id="02d47-130">Referência de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="02d47-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)