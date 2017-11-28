---
title: Listas (F#)
description: "Saiba mais sobre listas de F #, uma série de imutável, ordenada de elementos do mesmo tipo."
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a1a6075f-064d-4aee-8222-2b59ff16cc12
ms.openlocfilehash: 5802a5a1c48ad05c1765c4c0fa2e8a81a92dee8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="lists"></a><span data-ttu-id="7bd89-104">Listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-104">Lists</span></span>

> [!NOTE]
<span data-ttu-id="7bd89-105">Os links de referência da API neste artigo levarão você até o MSDN.</span><span class="sxs-lookup"><span data-stu-id="7bd89-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="7bd89-106">A referência da API docs.microsoft.com não está completa.</span><span class="sxs-lookup"><span data-stu-id="7bd89-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="7bd89-107">Uma lista em F# é uma série imutável, ordenada, de elementos do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="7bd89-107">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="7bd89-108">Para executar operações básicas em listas, use as funções no [módulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="7bd89-108">To perform basic operations on lists, use the functions in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>


## <a name="creating-and-initializing-lists"></a><span data-ttu-id="7bd89-109">Criando e inicializando listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-109">Creating and Initializing Lists</span></span>
<span data-ttu-id="7bd89-110">Você pode definir uma lista ao relacionar explicitamente os elementos, separados por ponto e vírgula e entre colchetes, como mostra a linha de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bd89-110">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="7bd89-111">Você também pode colocar quebras de linha entre os elementos, caso em que as vírgulas são opcionais.</span><span class="sxs-lookup"><span data-stu-id="7bd89-111">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="7bd89-112">A última sintaxe pode resultar em um código mais legível quando as expressões de inicialização de elemento são mais longas ou quando você quer incluir um comentário para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="7bd89-112">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="7bd89-113">Normalmente, todos os elementos da lista devem ser do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="7bd89-113">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="7bd89-114">Uma exceção existe quando uma lista em que os elementos são especificados para ser um tipo de base pode ter elementos do tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="7bd89-114">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="7bd89-115">Dessa forma, o que segue é aceitável, porque tanto `Button` quanto `CheckBox` derivam de `Control`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-115">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="7bd89-116">Você também pode definir os elementos da lista, usando um intervalo indicado por inteiros separados pelo operador de intervalo (`..`), como mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bd89-116">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="7bd89-117">Uma lista vazia é especificada por um par de colchetes sem nada entre eles.</span><span class="sxs-lookup"><span data-stu-id="7bd89-117">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="7bd89-118">Você também pode usar uma expressão de sequência para criar uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-118">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="7bd89-119">Consulte [expressões de sequência](sequences.md#sequence-expressions) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7bd89-119">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="7bd89-120">Por exemplo, o código a seguir cria uma lista dos quadrados de números inteiros de 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="7bd89-120">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="7bd89-121">Operadores para trabalhar com listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-121">Operators for Working with Lists</span></span>
<span data-ttu-id="7bd89-122">Você pode anexar elementos a uma lista usando o operador (cons) `::`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-122">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="7bd89-123">Se `list1` for `[2; 3; 4]`, o seguinte código criará `list2` como `[100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-123">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="7bd89-124">Você pode concatenar listas que possuem tipos compatíveis usando o operador `@`, como no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bd89-124">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="7bd89-125">Se `list1` for `[2; 3; 4]` e `list2` for `[100; 2; 3; 4 ]`, esse código criará `list3` como `[2; 3; 4; 100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-125">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4 ]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="7bd89-126">Funções para executar operações em listas estão disponíveis a [módulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="7bd89-126">Functions for performing operations on lists are available in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

<span data-ttu-id="7bd89-127">Como as listas em F# são imutáveis, quaisquer operações de modificação geram novas listas em vez de modificar as listas existentes.</span><span class="sxs-lookup"><span data-stu-id="7bd89-127">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="7bd89-128">Listas em F # são implementadas como listas encadeadas, o que significa que as operações que somente o início da lista de acesso são (1), e o acesso do elemento é O (*n*).</span><span class="sxs-lookup"><span data-stu-id="7bd89-128">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>


## <a name="properties"></a><span data-ttu-id="7bd89-129">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7bd89-129">Properties</span></span>
<span data-ttu-id="7bd89-130">O tipo de lista oferece suporte às seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="7bd89-130">The list type supports the following properties:</span></span>

|<span data-ttu-id="7bd89-131">Propriedade</span><span class="sxs-lookup"><span data-stu-id="7bd89-131">Property</span></span>|<span data-ttu-id="7bd89-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="7bd89-132">Type</span></span>|<span data-ttu-id="7bd89-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bd89-133">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="7bd89-134">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="7bd89-134">Head</span></span>](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|<span data-ttu-id="7bd89-135">O primeiro elemento.</span><span class="sxs-lookup"><span data-stu-id="7bd89-135">The first element.</span></span>|
|[<span data-ttu-id="7bd89-136">Vazio</span><span class="sxs-lookup"><span data-stu-id="7bd89-136">Empty</span></span>](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|<span data-ttu-id="7bd89-137">A propriedade estática que retorna uma lista vazia do tipo apropriado.</span><span class="sxs-lookup"><span data-stu-id="7bd89-137">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="7bd89-138">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="7bd89-138">IsEmpty</span></span>](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|<span data-ttu-id="7bd89-139">`true` se a lista não tiver elementos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-139">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="7bd89-140">Item</span><span class="sxs-lookup"><span data-stu-id="7bd89-140">Item</span></span>](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|<span data-ttu-id="7bd89-141">O elemento no índice especificado (com base em zero).</span><span class="sxs-lookup"><span data-stu-id="7bd89-141">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="7bd89-142">Comprimento</span><span class="sxs-lookup"><span data-stu-id="7bd89-142">Length</span></span>](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|<span data-ttu-id="7bd89-143">O número de elementos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-143">The number of elements.</span></span>|
|[<span data-ttu-id="7bd89-144">Final</span><span class="sxs-lookup"><span data-stu-id="7bd89-144">Tail</span></span>](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|<span data-ttu-id="7bd89-145">A lista sem o primeiro elemento.</span><span class="sxs-lookup"><span data-stu-id="7bd89-145">The list without the first element.</span></span>|
<span data-ttu-id="7bd89-146">A seguir, alguns exemplos de como usar essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="7bd89-146">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]
    
## <a name="using-lists"></a><span data-ttu-id="7bd89-147">Usando as listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-147">Using Lists</span></span>
<span data-ttu-id="7bd89-148">A programação com listas permite executar operações complexas com uma pequena quantidade de código.</span><span class="sxs-lookup"><span data-stu-id="7bd89-148">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="7bd89-149">Esta seção descreve operações comuns em listas que são importantes para programação funcional.</span><span class="sxs-lookup"><span data-stu-id="7bd89-149">This section describes common operations on lists that are important to functional programming.</span></span>


### <a name="recursion-with-lists"></a><span data-ttu-id="7bd89-150">Recursão com listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-150">Recursion with Lists</span></span>
<span data-ttu-id="7bd89-151">As listas são particularmente adequadas para técnicas de programação recursivas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-151">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="7bd89-152">Considere uma operação que deve ser executada em cada elemento de uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-152">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="7bd89-153">Você pode fazer isso de forma recursiva, operando no cabeçalho da lista e passando para a parte final da lista, que é uma lista menor que consiste na lista original, sem o primeiro elemento, e volte novamente ao próximo nível de recursão.</span><span class="sxs-lookup"><span data-stu-id="7bd89-153">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="7bd89-154">Para escrever uma função recursiva, você usa o operador cons (`::`) em correspondência de padrões, o que permite separar o cabeçalho de uma lista da parte final da lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-154">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="7bd89-155">O exemplo de código a seguir mostra como usar a correspondência de padrões para implementar uma função recursiva que executa operações em uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-155">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="7bd89-156">O código anterior funciona bem para pequenas listas, mas para listas maiores, pode estourar a pilha.</span><span class="sxs-lookup"><span data-stu-id="7bd89-156">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="7bd89-157">O código a seguir melhora este código usando um argumento acumulador, uma técnica padrão para trabalhar com funções recursivas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-157">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="7bd89-158">O uso do argumento acumulador torna a parte final da função recursiva, o que economiza espaço em pilha.</span><span class="sxs-lookup"><span data-stu-id="7bd89-158">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="7bd89-159">A função `RemoveAllMultiples` é uma função recursiva que usa duas listas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-159">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="7bd89-160">A primeira lista contém os números cujos múltiplos serão removidos e a segunda lista é a lista a partir da qual os números serão removidos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-160">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="7bd89-161">O código no exemplo a seguir usa essa função recursiva para eliminar todos os números não primos de uma lista, deixando uma lista de números primos como o resultado.</span><span class="sxs-lookup"><span data-stu-id="7bd89-161">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="7bd89-162">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-162">The output is as follows:</span></span>

```
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="7bd89-163">Funções do módulo</span><span class="sxs-lookup"><span data-stu-id="7bd89-163">Module Functions</span></span>
<span data-ttu-id="7bd89-164">O [módulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) fornece funções que acessam os elementos de uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-164">The [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) provides functions that access the elements of a list.</span></span> <span data-ttu-id="7bd89-165">O elemento cabeçalho é o mais rápido e fácil de acessar.</span><span class="sxs-lookup"><span data-stu-id="7bd89-165">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="7bd89-166">Use a propriedade [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) ou a função de módulo [head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span><span class="sxs-lookup"><span data-stu-id="7bd89-166">Use the property [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) or the module function [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span></span> <span data-ttu-id="7bd89-167">Você pode acessar a parte final de uma lista usando o [final](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) propriedade ou o [tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) função.</span><span class="sxs-lookup"><span data-stu-id="7bd89-167">You can access the tail of a list by using the [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) property or the [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) function.</span></span> <span data-ttu-id="7bd89-168">Para localizar um elemento por índice, use o [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) função.</span><span class="sxs-lookup"><span data-stu-id="7bd89-168">To find an element by index, use the [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) function.</span></span> <span data-ttu-id="7bd89-169">`List.nth` percorre a lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-169">`List.nth` traverses the list.</span></span> <span data-ttu-id="7bd89-170">Portanto, é O (*n*).</span><span class="sxs-lookup"><span data-stu-id="7bd89-170">Therefore, it is O(*n*).</span></span> <span data-ttu-id="7bd89-171">Se seu código usa `List.nth` com frequência, considere o uso de uma matriz em vez de uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-171">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="7bd89-172">O acesso de elemento em matrizes é O(1).</span><span class="sxs-lookup"><span data-stu-id="7bd89-172">Element access in arrays is O(1).</span></span>


### <a name="boolean-operations-on-lists"></a><span data-ttu-id="7bd89-173">Operações boolianas em listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-173">Boolean Operations on Lists</span></span>
<span data-ttu-id="7bd89-174">O [IsEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) função determina se uma lista tem todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-174">The [List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) function determines whether a list has any elements.</span></span>

<span data-ttu-id="7bd89-175">O [EXISTS](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) função se aplica a um valor booleano teste para elementos de uma lista e retorna `true` se qualquer elemento satisfaz o teste.</span><span class="sxs-lookup"><span data-stu-id="7bd89-175">The [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="7bd89-176">[Exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) é semelhante, mas funciona em pares sucessivas de elementos em duas listas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-176">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="7bd89-177">O código a seguir demonstra o uso de `List.exists`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-177">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="7bd89-178">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-178">The output is as follows:</span></span>

```
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="7bd89-179">O exemplo a seguir demonstra o uso de `List.exists2`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-179">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="7bd89-180">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-180">The output is as follows:</span></span>

```
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="7bd89-181">Você pode usar [ForAll](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) se você deseja testar se todos os elementos de uma lista de atenderem a uma condição.</span><span class="sxs-lookup"><span data-stu-id="7bd89-181">You can use [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="7bd89-182">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-182">The output is as follows:</span></span>

```
true
false
```

<span data-ttu-id="7bd89-183">Da mesma forma, [forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determina se todos os elementos em posições correspondentes em duas listas atendem uma expressão booleana que envolve a cada par de elementos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-183">Similarly, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="7bd89-184">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-184">The output is as follows:</span></span>

```
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="7bd89-185">Operações de classificação em listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-185">Sort Operations on Lists</span></span>
<span data-ttu-id="7bd89-186">O [Sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [SortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), e [sortwith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) funções classificar listas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-186">The [List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), and [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) functions sort lists.</span></span> <span data-ttu-id="7bd89-187">A função de classificação determina qual dessas três funções usar.</span><span class="sxs-lookup"><span data-stu-id="7bd89-187">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="7bd89-188">`List.sort` usa uma comparação genérica padrão.</span><span class="sxs-lookup"><span data-stu-id="7bd89-188">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="7bd89-189">A comparação genérica utiliza operadores globais com base na função de comparação genérica para comparar valores.</span><span class="sxs-lookup"><span data-stu-id="7bd89-189">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="7bd89-190">Funciona de forma eficiente com uma grande variedade de tipos de elementos, tais como tipos numéricos simples, tuplas, registros, uniões discriminadas, listas, matrizes e qualquer tipo que implementa `System.IComparable`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-190">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="7bd89-191">Para os tipos que implementam `System.IComparable`, a comparação genérica usa a função `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-191">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="7bd89-192">A comparação genérica também funciona com cadeias de caracteres, mas usa uma ordem de classificação independente de cultura.</span><span class="sxs-lookup"><span data-stu-id="7bd89-192">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="7bd89-193">A comparação genérica não deve ser usada em tipos sem suporte, como os tipos de função.</span><span class="sxs-lookup"><span data-stu-id="7bd89-193">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="7bd89-194">Além disso, o desempenho da comparação genérica padrão é melhor para tipos estruturados pequenos; para tipos estruturados maiores que precisam ser comparados e classificados com frequência, considere implementar `System.IComparable` e fornecer uma implementação eficiente do método `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-194">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="7bd89-195">`List.sortBy` usa uma função que retorna um valor usado como critério de classificação e `List.sortWith` assume uma função de comparação como argumento.</span><span class="sxs-lookup"><span data-stu-id="7bd89-195">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="7bd89-196">Essas duas últimas funções são úteis quando você está trabalhando com tipos que não suportam comparação ou quando a comparação requer mais semântica de comparação complexa, como é o caso das cadeias de caracteres com reconhecimento de cultura.</span><span class="sxs-lookup"><span data-stu-id="7bd89-196">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="7bd89-197">O exemplo a seguir demonstra o uso de `List.sort`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-197">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="7bd89-198">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-198">The output is as follows:</span></span>

```
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="7bd89-199">O exemplo a seguir demonstra o uso de `List.sortBy`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-199">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="7bd89-200">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-200">The output is as follows:</span></span>

```
[1; -2; 4; 5; 8]
```

<span data-ttu-id="7bd89-201">O exemplo a seguir demonstra o uso de `List.sortWith`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-201">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="7bd89-202">Neste exemplo, a função de comparação personalizada `compareWidgets` é usada para comparar um primeiro campo de um tipo personalizado e depois outro, quando os valores do primeiro campo são iguais.</span><span class="sxs-lookup"><span data-stu-id="7bd89-202">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="7bd89-203">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-203">The output is as follows:</span></span>

```
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="7bd89-204">Operações de pesquisa em listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-204">Search Operations on Lists</span></span>
<span data-ttu-id="7bd89-205">Várias operações de pesquisa têm suporte para listas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-205">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="7bd89-206">A forma mais simples, [Find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), permite que você localize o primeiro elemento que corresponde a uma determinada condição.</span><span class="sxs-lookup"><span data-stu-id="7bd89-206">The simplest, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="7bd89-207">O exemplo de código a seguir demonstra o uso de `List.find` para encontrar o primeiro número divisível por 5 em uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-207">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="7bd89-208">O resultado é 5.</span><span class="sxs-lookup"><span data-stu-id="7bd89-208">The result is 5.</span></span>

<span data-ttu-id="7bd89-209">Se os elementos devem ser transformados primeiro, chame [Pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), que usa uma função que retorna uma opção e valor de procura a primeira opção que é `Some(x)`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-209">If the elements must be transformed first, call [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="7bd89-210">Em vez de retornar o elemento, `List.pick` retorna o resultado `x`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-210">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="7bd89-211">Se nenhum elemento correspondente for encontrado, `List.pick` lançará `System.Collections.Generic.KeyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-211">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="7bd89-212">O código a seguir demonstra o uso de `List.pick`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-212">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="7bd89-213">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-213">The output is as follows:</span></span>

```
"b"
```

<span data-ttu-id="7bd89-214">Outro grupo de operações de pesquisa, [tryfind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) e funções relacionadas, retornar um valor de opção.</span><span class="sxs-lookup"><span data-stu-id="7bd89-214">Another group of search operations, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) and related functions, return an option value.</span></span> <span data-ttu-id="7bd89-215">A função `List.tryFind` retorna o primeiro elemento de uma lista que satisfaz a uma condição se tal elemento existir, mas retorna o valor da opção `None` se o elemento não existir.</span><span class="sxs-lookup"><span data-stu-id="7bd89-215">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="7bd89-216">A variação [tryfindindex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) retorna o índice do elemento, caso seja encontrado, em vez do próprio elemento.</span><span class="sxs-lookup"><span data-stu-id="7bd89-216">The variation [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="7bd89-217">Essas funções são ilustradas no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7bd89-217">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="7bd89-218">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-218">The output is as follows:</span></span>

```
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="7bd89-219">Operações aritméticas em listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-219">Arithmetic Operations on Lists</span></span>
<span data-ttu-id="7bd89-220">Operações aritméticas comuns, como soma e média são incorporadas a [módulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="7bd89-220">Common arithmetic operations such as sum and average are built into the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="7bd89-221">Para trabalhar com [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), o tipo de elemento de lista deve oferecer suporte a `+` operador e ter um valor igual a zero.</span><span class="sxs-lookup"><span data-stu-id="7bd89-221">To work with [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="7bd89-222">Todos os tipos aritméticos internos satisfazem a essas condições.</span><span class="sxs-lookup"><span data-stu-id="7bd89-222">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="7bd89-223">Para trabalhar com [Average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), o tipo de elemento deve oferecer suporte a divisão sem resto, que permite que os tipos de ponto flutuante, mas exclui tipos integrais.</span><span class="sxs-lookup"><span data-stu-id="7bd89-223">To work with [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="7bd89-224">O [sumby](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) e [averageby](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) funções usam uma função como um parâmetro e os resultados desta função são usados para calcular os valores para a soma ou média.</span><span class="sxs-lookup"><span data-stu-id="7bd89-224">The [List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) and [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="7bd89-225">O código a seguir demonstra o uso de `List.sum`, `List.sumBy` e `List.average`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-225">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="7bd89-226">A saída é `1.000000`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-226">The output is `1.000000`.</span></span>

<span data-ttu-id="7bd89-227">O código a seguir demonstra o uso de `List.averageBy`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-227">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="7bd89-228">A saída é `5.5`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-228">The output is `5.5`.</span></span>


### <a name="lists-and-tuples"></a><span data-ttu-id="7bd89-229">Listas e tuplas</span><span class="sxs-lookup"><span data-stu-id="7bd89-229">Lists and Tuples</span></span>
<span data-ttu-id="7bd89-230">As listas que contêm tuplas podem ser manipuladas pelas funções de compactação e descompactação.</span><span class="sxs-lookup"><span data-stu-id="7bd89-230">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="7bd89-231">Essas funções combinam duas listas de valores únicos em uma lista de tuplas ou separam uma lista de tuplas em duas listas de valores únicos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-231">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="7bd89-232">A forma mais simples [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) função usa duas listas de elementos únicos e produz uma lista de pares de tupla.</span><span class="sxs-lookup"><span data-stu-id="7bd89-232">The simplest [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="7bd89-233">Outra versão, [zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), usa três listas de elementos únicos e produz uma lista de tuplas que têm três elementos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-233">Another version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="7bd89-234">O exemplo de código a seguir demonstra o uso de `List.zip`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-234">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="7bd89-235">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-235">The output is as follows:</span></span>

```
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="7bd89-236">O exemplo de código a seguir demonstra o uso de `List.zip3`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-236">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="7bd89-237">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-237">The output is as follows:</span></span>

```
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="7bd89-238">O correspondente Descompacte versões, [Unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) e [unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), siga a lista de tuplas e retornar a lista em uma tupla, onde a primeira lista contém todos os elementos que estavam primeiras no cada tupla e o segunda lista contém o segundo elemento de cada tupla e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="7bd89-238">The corresponding unzip versions, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) and [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="7bd89-239">O exemplo de código a seguir demonstra o uso de [Unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span><span class="sxs-lookup"><span data-stu-id="7bd89-239">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="7bd89-240">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-240">The output is as follows:</span></span>

```
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="7bd89-241">O exemplo de código a seguir demonstra o uso de [unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span><span class="sxs-lookup"><span data-stu-id="7bd89-241">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="7bd89-242">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-242">The output is as follows:</span></span>

```
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="7bd89-243">Operando em elementos de lista</span><span class="sxs-lookup"><span data-stu-id="7bd89-243">Operating on List Elements</span></span>
<span data-ttu-id="7bd89-244">F# oferece suporte a uma variedade de operações em elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-244">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="7bd89-245">É mais simples [iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), que permite que você chamar uma função em cada elemento de uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-245">The simplest is [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="7bd89-246">Incluem variações [iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), que permite que você execute uma operação em elementos de duas listas, [iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), como `List.iter` exceto que o índice de cada elemento é passado como um argumento da função que é chamado para cada elemento, e [iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), que é uma combinação da funcionalidade do `List.iter2` e `List.iteri`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-246">Variations include [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), which enables you to perform an operation on elements of two lists, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="7bd89-247">O exemplo de código a seguir ilustra essas funções.</span><span class="sxs-lookup"><span data-stu-id="7bd89-247">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="7bd89-248">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-248">The output is as follows:</span></span>

```
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="7bd89-249">Outra função usada com frequência que transforma os elementos da lista é [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), que permite que você aplicar uma função para cada elemento de uma lista e colocar todos os resultados em uma nova lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-249">Another frequently used function that transforms list elements is [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="7bd89-250">[Map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) e [map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) são variações que usam várias listas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-250">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) and [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) are variations that take multiple lists.</span></span> <span data-ttu-id="7bd89-251">Você também pode usar [MAPI](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) e [mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), se, além do elemento, a função deverá ser passado o índice de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="7bd89-251">You can also use [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) and [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="7bd89-252">A única diferença entre `List.mapi2` e `List.mapi` é que `List.mapi2` funciona com as duas listas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-252">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="7bd89-253">O exemplo a seguir ilustra [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span><span class="sxs-lookup"><span data-stu-id="7bd89-253">The following example illustrates [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="7bd89-254">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-254">The output is as follows:</span></span>

```
[2; 3; 4]
```

<span data-ttu-id="7bd89-255">O exemplo a seguir demonstra o uso de `List.map2`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-255">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="7bd89-256">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-256">The output is as follows:</span></span>

```
[5; 7; 9]
```

<span data-ttu-id="7bd89-257">O exemplo a seguir demonstra o uso de `List.map3`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-257">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="7bd89-258">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-258">The output is as follows:</span></span>

```
[7; 10; 13]
```

<span data-ttu-id="7bd89-259">O exemplo a seguir demonstra o uso de `List.mapi`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-259">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="7bd89-260">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-260">The output is as follows:</span></span>

```
[1; 3; 5]
```

<span data-ttu-id="7bd89-261">O exemplo a seguir demonstra o uso de `List.mapi2`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-261">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="7bd89-262">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-262">The output is as follows:</span></span>

```
[0; 7; 18]
```

<span data-ttu-id="7bd89-263">[Collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) é como `List.map`, exceto pelo fato de cada elemento gera uma lista e todas essas listas são concatenadas em uma lista final.</span><span class="sxs-lookup"><span data-stu-id="7bd89-263">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="7bd89-264">No código a seguir, cada elemento da lista gera três números.</span><span class="sxs-lookup"><span data-stu-id="7bd89-264">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="7bd89-265">Eles são todos coletados em uma única lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-265">These are all collected into one list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="7bd89-266">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-266">The output is as follows:</span></span>

```
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="7bd89-267">Você também pode usar [List](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), que usa uma condição booleana e produz uma nova lista que consiste apenas em elementos que atendem à condição fornecida.</span><span class="sxs-lookup"><span data-stu-id="7bd89-267">You can also use [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="7bd89-268">A lista resultante é `[2; 4; 6]`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-268">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="7bd89-269">Uma combinação de mapa e filtro, [Choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) permite transformar e selecionar elementos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="7bd89-269">A combination of map and filter, [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="7bd89-270">`List.choose` aplica uma função que retorna uma opção para cada elemento de uma lista e retorna uma nova lista de resultados para os elementos quando a função retorna o valor de opção `Some`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-270">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="7bd89-271">O código a seguir demonstra o uso de `List.choose` para selecionar palavras em maiúsculas a partir de uma lista de palavras.</span><span class="sxs-lookup"><span data-stu-id="7bd89-271">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="7bd89-272">A saída é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="7bd89-272">The output is as follows:</span></span>

```
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="7bd89-273">Operando em várias listas</span><span class="sxs-lookup"><span data-stu-id="7bd89-273">Operating on Multiple Lists</span></span>
<span data-ttu-id="7bd89-274">As listas podem ser reunidas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-274">Lists can be joined together.</span></span> <span data-ttu-id="7bd89-275">Para unir duas listas em um, usar [append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span><span class="sxs-lookup"><span data-stu-id="7bd89-275">To join two lists into one, use [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span></span> <span data-ttu-id="7bd89-276">Para adicionar mais de duas listas, use [concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span><span class="sxs-lookup"><span data-stu-id="7bd89-276">To join more than two lists, use [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet26.fs)]
    
### <a name="fold-and-scan-operations"></a><span data-ttu-id="7bd89-277">Operações de dobra e digitalização</span><span class="sxs-lookup"><span data-stu-id="7bd89-277">Fold and Scan Operations</span></span>
<span data-ttu-id="7bd89-278">Algumas operações de lista envolvem interdependências entre todos os elementos da lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-278">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="7bd89-279">As operações de verificação e dobra são como `List.iter` e `List.map` em que você chamar uma função em cada elemento, mas essas operações fornecem um parâmetro adicional chamado a *acumulador* que contém informações por meio de o cálculo.</span><span class="sxs-lookup"><span data-stu-id="7bd89-279">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="7bd89-280">Use `List.fold` para executar um cálculo em uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-280">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="7bd89-281">O exemplo de código a seguir demonstra o uso de [Fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) para executar várias operações.</span><span class="sxs-lookup"><span data-stu-id="7bd89-281">The following code example demonstrates the use of [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) to perform various operations.</span></span>

<span data-ttu-id="7bd89-282">A lista é percorrida; o acumulador `acc` é um valor passado conforme ocorre o progresso do cálculo.</span><span class="sxs-lookup"><span data-stu-id="7bd89-282">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="7bd89-283">O primeiro argumento usa o acumulador e o elemento da lista, retornando o resultado intermediário do cálculo para esse elemento da lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-283">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="7bd89-284">O segundo argumento é o valor inicial do acumulador.</span><span class="sxs-lookup"><span data-stu-id="7bd89-284">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="7bd89-285">As versões dessas funções que têm um dígito no nome da função operam em mais de uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-285">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="7bd89-286">Por exemplo, [fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) executa cálculos em duas listas.</span><span class="sxs-lookup"><span data-stu-id="7bd89-286">For example, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) performs computations on two lists.</span></span>

<span data-ttu-id="7bd89-287">O exemplo a seguir demonstra o uso de `List.fold2`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-287">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="7bd89-288">`List.fold`e [Scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) diferem no que `List.fold` retorna o valor final do parâmetro extra, mas `List.scan` retorna a lista dos valores intermediários (junto com o valor final) do parâmetro extra.</span><span class="sxs-lookup"><span data-stu-id="7bd89-288">`List.fold` and [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="7bd89-289">Cada uma dessas funções inclui uma variação reversa, por exemplo, [foldback](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), que é diferente na ordem em que a lista é atravessada e a ordem dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-289">Each of these functions includes a reverse variation, for example, [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="7bd89-290">Além disso, `List.fold` e `List.foldBack` ter variações, [fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) e [foldback2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), que levar duas listas de comprimento igual.</span><span class="sxs-lookup"><span data-stu-id="7bd89-290">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) and [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), that take two lists of equal length.</span></span> <span data-ttu-id="7bd89-291">A função executada em cada elemento pode usar elementos correspondentes das duas listas para realizar alguma ação.</span><span class="sxs-lookup"><span data-stu-id="7bd89-291">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="7bd89-292">Os tipos de elementos das duas listas podem ser diferentes, como no exemplo a seguir, em que uma lista contém valores de transação de uma conta bancária e a outra lista contém o tipo de transação: depósito ou retirada.</span><span class="sxs-lookup"><span data-stu-id="7bd89-292">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="7bd89-293">Para um cálculo como somatória, `List.fold` e `List.foldBack` têm o mesmo efeito, porque o resultado não depende da ordem de passagem.</span><span class="sxs-lookup"><span data-stu-id="7bd89-293">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="7bd89-294">No exemplo a seguir, `List.foldBack` é usado para adicionar os elementos em uma lista.</span><span class="sxs-lookup"><span data-stu-id="7bd89-294">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="7bd89-295">O exemplo a seguir retorna ao exemplo da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="7bd89-295">The following example returns to the bank account example.</span></span> <span data-ttu-id="7bd89-296">Desta vez, um novo tipo de transação é adicionado: cálculo de juros.</span><span class="sxs-lookup"><span data-stu-id="7bd89-296">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="7bd89-297">O saldo final agora depende da ordem das transações.</span><span class="sxs-lookup"><span data-stu-id="7bd89-297">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="7bd89-298">A função [reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) é um pouco como `List.fold` e `List.scan`, exceto que, em vez de passar um acumulador separado, `List.reduce` usa uma função que leva dois argumentos de tipo de elemento, em vez de apenas um e um desses argumentos atua como acumulador, que significa que ele armazena o resultado intermediário da computação.</span><span class="sxs-lookup"><span data-stu-id="7bd89-298">The function [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="7bd89-299">`List.reduce` começa a operar nos dois primeiros elementos da lista e, em seguida, usa o resultado da operação juntamente com o próximo elemento.</span><span class="sxs-lookup"><span data-stu-id="7bd89-299">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="7bd89-300">Como não há um acumulador separado que tem o seu próprio tipo, `List.reduce` pode ser usado no lugar de `List.fold` somente quando o acumulador e o tipo de elemento têm o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="7bd89-300">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="7bd89-301">O código a seguir demonstra o uso de `List.reduce`.</span><span class="sxs-lookup"><span data-stu-id="7bd89-301">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="7bd89-302">`List.reduce` lançará uma exceção se a lista fornecida não tiver elementos.</span><span class="sxs-lookup"><span data-stu-id="7bd89-302">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="7bd89-303">No código a seguir, a primeira chamada para a expressão lambda recebeu os argumentos 2 e 4, retornando 6 e a chamada seguinte recebeu os argumentos 6 e 10, de modo que o resultado é 16.</span><span class="sxs-lookup"><span data-stu-id="7bd89-303">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet33.fs)]
    
### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="7bd89-304">Convertendo entre listas e outros tipos de coleção</span><span class="sxs-lookup"><span data-stu-id="7bd89-304">Converting Between Lists and Other Collection Types</span></span>
<span data-ttu-id="7bd89-305">O módulo `List` fornece funções para converter de e para sequências e matrizes.</span><span class="sxs-lookup"><span data-stu-id="7bd89-305">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="7bd89-306">Para converter de ou para uma sequência, use [toseq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) ou [ofseq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span><span class="sxs-lookup"><span data-stu-id="7bd89-306">To convert to or from a sequence, use [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) or [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span></span> <span data-ttu-id="7bd89-307">Para converter de ou para uma matriz, use [ToArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) ou [ofarray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span><span class="sxs-lookup"><span data-stu-id="7bd89-307">To convert to or from an array, use [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) or [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span></span>


### <a name="additional-operations"></a><span data-ttu-id="7bd89-308">Operações adicionais</span><span class="sxs-lookup"><span data-stu-id="7bd89-308">Additional Operations</span></span>
<span data-ttu-id="7bd89-309">Para obter informações sobre operações adicionais em listas, consulte o tópico de referência da biblioteca [módulo Collections. List](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="7bd89-309">For information about additional operations on lists, see the library reference topic [Collections.List Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span></span>


## <a name="see-also"></a><span data-ttu-id="7bd89-310">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7bd89-310">See Also</span></span>
[<span data-ttu-id="7bd89-311">Referência da Linguagem F#</span><span class="sxs-lookup"><span data-stu-id="7bd89-311">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="7bd89-312">Tipos F#</span><span class="sxs-lookup"><span data-stu-id="7bd89-312">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="7bd89-313">Sequências</span><span class="sxs-lookup"><span data-stu-id="7bd89-313">Sequences</span></span>](sequences.md)

[<span data-ttu-id="7bd89-314">Matrizes</span><span class="sxs-lookup"><span data-stu-id="7bd89-314">Arrays</span></span>](arrays.md)

[<span data-ttu-id="7bd89-315">Opções</span><span class="sxs-lookup"><span data-stu-id="7bd89-315">Options</span></span>](options.md)