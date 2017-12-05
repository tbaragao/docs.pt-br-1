---
title: "Conversões cast e conversões (F#)"
description: "Saiba como o F # linguagem de programação fornece os operadores de conversão para conversões aritméticas entre vários tipos primitivos."
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: f17d3919c59c5881213d28a59cea7ae184493949
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="63739-104">Conversões cast e conversões (F#)</span><span class="sxs-lookup"><span data-stu-id="63739-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="63739-105">Este tópico descreve o suporte para conversões de tipo em F #.</span><span class="sxs-lookup"><span data-stu-id="63739-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="63739-106">Tipos aritméticos</span><span class="sxs-lookup"><span data-stu-id="63739-106">Arithmetic Types</span></span>
<span data-ttu-id="63739-107">F # fornece os operadores de conversão para conversões aritméticas entre vários tipos primitivos, como entre inteiro e tipos de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="63739-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="63739-108">Os operadores de conversão integral e char verificou e formulários desmarcados; o ponto flutuante operadores e `enum` operador de conversão não.</span><span class="sxs-lookup"><span data-stu-id="63739-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="63739-109">Os formulários não verificados são definidos em `Microsoft.FSharp.Core.Operators` e formulários de ativação são definidos em `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="63739-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="63739-110">Os formulários check verificar estouro e geram uma exceção de tempo de execução se o valor resultante exceder os limites do tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="63739-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="63739-111">Cada um desses operadores tem o mesmo nome que o nome do tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="63739-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="63739-112">Por exemplo, no código a seguir, no qual os tipos são explicitamente anotados, `byte` aparece com dois significados diferentes.</span><span class="sxs-lookup"><span data-stu-id="63739-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="63739-113">A primeira ocorrência é o tipo e o segundo é o operador de conversão.</span><span class="sxs-lookup"><span data-stu-id="63739-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="63739-114">A tabela a seguir mostra os operadores de conversão definidos em F #.</span><span class="sxs-lookup"><span data-stu-id="63739-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="63739-115">Operador</span><span class="sxs-lookup"><span data-stu-id="63739-115">Operator</span></span>|<span data-ttu-id="63739-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="63739-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="63739-117">Converta em bytes, um tipo não assinado de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="63739-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="63739-118">Converta em byte assinado.</span><span class="sxs-lookup"><span data-stu-id="63739-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="63739-119">Converta em um inteiro assinado de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="63739-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="63739-120">Converta em um inteiro não assinado de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="63739-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="63739-121">Converta em um inteiro assinado de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="63739-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="63739-122">Converta em um inteiro não assinado de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="63739-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="63739-123">Converta em um inteiro assinado de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="63739-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="63739-124">Converta em um inteiro não assinado de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="63739-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="63739-125">Converta em um inteiro nativo.</span><span class="sxs-lookup"><span data-stu-id="63739-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="63739-126">Converta em um inteiro não assinado de nativo.</span><span class="sxs-lookup"><span data-stu-id="63739-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="63739-127">Converta em um IEEE de precisão dupla de 64 bits número de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="63739-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="63739-128">Converta em um IEEE de precisão simples de 32 bits número de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="63739-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="63739-129">Converter em `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63739-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="63739-130">Converter em `System.Char`, um caractere Unicode.</span><span class="sxs-lookup"><span data-stu-id="63739-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="63739-131">Converta em um tipo enumerado.</span><span class="sxs-lookup"><span data-stu-id="63739-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="63739-132">Além de tipos primitivos internos, você pode usar esses operadores com tipos que implementam `op_Explicit` ou `op_Implicit` métodos com as assinaturas apropriadas.</span><span class="sxs-lookup"><span data-stu-id="63739-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="63739-133">Por exemplo, o `int` operador de conversão funciona com qualquer tipo que fornece um método estático `op_Explicit` que usa o tipo como um parâmetro e retorna `int`.</span><span class="sxs-lookup"><span data-stu-id="63739-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="63739-134">Como uma exceção especial para a regra geral que métodos não podem ser sobrecarregados pelo tipo de retorno, você pode fazer isso `op_Explicit` e `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="63739-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="63739-135">Tipos enumerados</span><span class="sxs-lookup"><span data-stu-id="63739-135">Enumerated Types</span></span>
<span data-ttu-id="63739-136">O `enum` operador é um operador genérico que recebe um parâmetro de tipo que representa o tipo do `enum` para converter.</span><span class="sxs-lookup"><span data-stu-id="63739-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="63739-137">Ao converter para um tipo enumerado, digite inferência tenta determinar o tipo do `enum` que você deseja converter.</span><span class="sxs-lookup"><span data-stu-id="63739-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="63739-138">No exemplo a seguir, a variável `col1` não é anotado explicitamente, mas seu tipo é inferido do teste de igualdade posterior.</span><span class="sxs-lookup"><span data-stu-id="63739-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="63739-139">Portanto, o compilador pode deduzir que estiver convertendo um `Color` enumeração.</span><span class="sxs-lookup"><span data-stu-id="63739-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="63739-140">Como alternativa, você pode fornecer uma anotação de tipo, assim como acontece com `col2` no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="63739-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="63739-141">Você também pode especificar o tipo de enumeração de destino explicitamente como um parâmetro de tipo, como o código a seguir:</span><span class="sxs-lookup"><span data-stu-id="63739-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="63739-142">Observe que a enumeração converte trabalho somente se o tipo subjacente da enumeração é compatível com o tipo que está sendo convertido.</span><span class="sxs-lookup"><span data-stu-id="63739-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="63739-143">No código a seguir, a conversão não compila devido a incompatibilidade entre `int32` e `uint32`.</span><span class="sxs-lookup"><span data-stu-id="63739-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="63739-144">Para obter mais informações, consulte [enumerações](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="63739-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="63739-145">Conversão de tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="63739-145">Casting Object Types</span></span>
<span data-ttu-id="63739-146">Conversão entre tipos em uma hierarquia de objetos é fundamental para programação orientada a objeto.</span><span class="sxs-lookup"><span data-stu-id="63739-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="63739-147">Há dois tipos básicos de conversões: conversão de (upcasting) e a conversão para baixo (Baixar).</span><span class="sxs-lookup"><span data-stu-id="63739-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="63739-148">Conversão de uma hierarquia significa a projeção de uma referência de objeto derivado de uma referência de objeto base.</span><span class="sxs-lookup"><span data-stu-id="63739-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="63739-149">Uma conversão é garantida como a classe base é na hierarquia de herança da classe derivada.</span><span class="sxs-lookup"><span data-stu-id="63739-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="63739-150">Conversão de uma hierarquia, de uma referência de objeto base para uma referência de objeto derivado é realizada somente se o objeto é, na verdade, uma instância do tipo de destino correto (derivado) ou um tipo derivado do tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="63739-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="63739-151">F # fornece operadores para esses tipos de conversões.</span><span class="sxs-lookup"><span data-stu-id="63739-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="63739-152">O `:>` operador converte a hierarquia e o `:?>` operador converte abaixo na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="63739-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="63739-153">Upcasting</span><span class="sxs-lookup"><span data-stu-id="63739-153">Upcasting</span></span>
<span data-ttu-id="63739-154">Em muitas linguagens orientada a objeto upcasting é implícita; em F #, as regras são ligeiramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="63739-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="63739-155">Upcasting é aplicada automaticamente quando você passar argumentos para métodos em um tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="63739-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="63739-156">No entanto, para funções associados a let em um módulo, upcasting não é automática, a menos que o tipo de parâmetro é declarado como um tipo flexível.</span><span class="sxs-lookup"><span data-stu-id="63739-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="63739-157">Para obter mais informações, consulte [tipos flexíveis](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="63739-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="63739-158">O `:>` operador executa estático cast, o que significa que o sucesso da conversão é determinado em tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="63739-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="63739-159">Se uma conversão que usa `:>` compilado com êxito, ela é uma conversão válida e não tem nenhuma possibilidade de falha em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="63739-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="63739-160">Você também pode usar o `upcast` operador para executar tal conversão.</span><span class="sxs-lookup"><span data-stu-id="63739-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="63739-161">A expressão a seguir especifica uma conversão da hierarquia:</span><span class="sxs-lookup"><span data-stu-id="63739-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="63739-162">Quando você usa o operador upcast, o compilador tenta inferir o tipo que estiver convertendo do contexto.</span><span class="sxs-lookup"><span data-stu-id="63739-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="63739-163">Se o compilador não puder determinar o tipo de destino, o compilador relata um erro.</span><span class="sxs-lookup"><span data-stu-id="63739-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="63739-164">Baixar</span><span class="sxs-lookup"><span data-stu-id="63739-164">Downcasting</span></span>
<span data-ttu-id="63739-165">O `:?>` operador executa um dinâmico cast, o que significa que o sucesso da conversão é determinado em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="63739-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="63739-166">Uma conversão que usa o `:?>` operador não é verificado no tempo de compilação; mas em tempo de execução, é feita uma tentativa de converter para o tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="63739-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="63739-167">Se o objeto é compatível com o tipo de destino, a conversão for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="63739-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="63739-168">Se o objeto não é compatível com o tipo de destino, o tempo de execução gera um `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="63739-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="63739-169">Você também pode usar o `downcast` operador para executar uma conversão de tipo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="63739-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="63739-170">A expressão a seguir especifica uma conversão abaixo na hierarquia para um tipo que é inferido do contexto do programa:</span><span class="sxs-lookup"><span data-stu-id="63739-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="63739-171">Para o `upcast` operador, se o compilador não é possível inferir um tipo de destino específico do contexto, ele relatará um erro.</span><span class="sxs-lookup"><span data-stu-id="63739-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="63739-172">O código a seguir ilustra o uso do `:>` e `:?>` operadores.</span><span class="sxs-lookup"><span data-stu-id="63739-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="63739-173">O código ilustra que o `:?>` operador é mais útil quando você sabe que a conversão seja bem-sucedida, porque ele lança `InvalidCastException` se a conversão falhar.</span><span class="sxs-lookup"><span data-stu-id="63739-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="63739-174">Se você não souber que uma conversão seja bem-sucedida, um teste de tipo que usa um `match` expressão é melhor porque ela evita a sobrecarga de gerar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="63739-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="63739-175">Como operadores genéricos `downcast` e `upcast` dependem de inferência de tipo para determinar o tipo de argumento e retornar, no código acima, você pode substituir</span><span class="sxs-lookup"><span data-stu-id="63739-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="63739-176">with</span><span class="sxs-lookup"><span data-stu-id="63739-176">with</span></span>

```fsharp
base1 = upcast d1
```

<span data-ttu-id="63739-177">No código anterior, o tipo de argumento e tipos de retorno são `Derived1` e `Base1`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="63739-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="63739-178">Para obter mais informações sobre testes de tipo, consulte [correspondência expressões](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="63739-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="63739-179">Consulte também</span><span class="sxs-lookup"><span data-stu-id="63739-179">See Also</span></span>
[<span data-ttu-id="63739-180">Referência da Linguagem F#</span><span class="sxs-lookup"><span data-stu-id="63739-180">F# Language Reference</span></span>](index.md)