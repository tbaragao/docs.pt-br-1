---
title: 'Gerenciamento de recursos: a palavra-chave use (F#)'
description: "Saiba mais sobre o F # palavra-chave 'use' e a função 'usando', que pode controlar a inicialização e a liberação de recursos."
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 00c3040e-859f-4dad-a7b5-7b8d44dc232c
ms.openlocfilehash: d4e8626f07f1c77e52e8fabd5ccc07dbf1fa8ddd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="4146c-104">Gerenciamento de recursos: a palavra-chave use</span><span class="sxs-lookup"><span data-stu-id="4146c-104">Resource Management: The use Keyword</span></span>

<span data-ttu-id="4146c-105">Este tópico descreve a palavra-chave `use` e `using` função, que pode controlar a inicialização e a liberação de recursos.</span><span class="sxs-lookup"><span data-stu-id="4146c-105">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="4146c-106">Recursos</span><span class="sxs-lookup"><span data-stu-id="4146c-106">Resources</span></span>
<span data-ttu-id="4146c-107">O termo *recurso* é usado em mais de uma maneira.</span><span class="sxs-lookup"><span data-stu-id="4146c-107">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="4146c-108">Sim, os recursos podem ser dados que usa um aplicativo, como cadeias de caracteres, gráficos e assim por diante, mas nesse contexto, *recursos* refere-se aos recursos de software ou sistema operacional, como os contextos de dispositivo de gráficos, identificadores de arquivos, rede banco de dados e conexões, objetos de simultaneidade, como identificadores de espera e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4146c-108">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="4146c-109">O uso desses recursos por aplicativos envolve a aquisição de recursos do sistema operacional ou outro provedor de recursos, seguido da versão mais recente do recurso para o pool para que ele pode ser fornecido para outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4146c-109">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="4146c-110">Ocorrer problemas quando os aplicativos não liberar recursos de volta para o pool comum.</span><span class="sxs-lookup"><span data-stu-id="4146c-110">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="4146c-111">Gerenciamento de recursos</span><span class="sxs-lookup"><span data-stu-id="4146c-111">Managing Resources</span></span>
<span data-ttu-id="4146c-112">Para e de forma eficiente com responsabilidade gerenciar recursos em um aplicativo, você deve liberar recursos imediatamente e de maneira previsível.</span><span class="sxs-lookup"><span data-stu-id="4146c-112">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="4146c-113">O .NET Framework ajuda você a fazer isso, fornecendo o `System.IDisposable` interface.</span><span class="sxs-lookup"><span data-stu-id="4146c-113">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="4146c-114">Um tipo que implementa `System.IDisposable` tem o `System.IDisposable.Dispose` método, o que libera corretamente os recursos.</span><span class="sxs-lookup"><span data-stu-id="4146c-114">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="4146c-115">Aplicativos escritos bem garantem que `System.IDisposable.Dispose` é chamado imediatamente quando qualquer objeto que contém um recurso limitado não for mais necessário.</span><span class="sxs-lookup"><span data-stu-id="4146c-115">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="4146c-116">Felizmente, a maioria das linguagens .NET fornecem suporte para facilitar essa tarefa, e F # não é exceção.</span><span class="sxs-lookup"><span data-stu-id="4146c-116">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="4146c-117">Há duas construções de linguagem úteis que suportam o padrão dispose: o `use` associação e o `using` função.</span><span class="sxs-lookup"><span data-stu-id="4146c-117">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="4146c-118">usar associação</span><span class="sxs-lookup"><span data-stu-id="4146c-118">use Binding</span></span>
<span data-ttu-id="4146c-119">O `use` palavra-chave tem um formulário que se assemelha a do `let` associação:</span><span class="sxs-lookup"><span data-stu-id="4146c-119">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="4146c-120">Use *valor* = *expressão*</span><span class="sxs-lookup"><span data-stu-id="4146c-120">use *value* = *expression*</span></span>

<span data-ttu-id="4146c-121">Ele fornece a mesma funcionalidade de um `let` de associação, mas adiciona uma chamada para `Dispose` no valor quando o valor sai do escopo.</span><span class="sxs-lookup"><span data-stu-id="4146c-121">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="4146c-122">Observe que o compilador insere uma verificação de nulos no valor, para que, se o valor seja `null`, a chamada para `Dispose` não é realizada.</span><span class="sxs-lookup"><span data-stu-id="4146c-122">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="4146c-123">O exemplo a seguir mostra como fechar um arquivo automaticamente usando o `use` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="4146c-123">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
<span data-ttu-id="4146c-124">Você pode usar `use` em expressões de cálculo, caso em que uma versão personalizada do `use` expressão é usada.</span><span class="sxs-lookup"><span data-stu-id="4146c-124">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="4146c-125">Para obter mais informações, consulte [sequências](sequences.md), [fluxos de trabalho assíncronos](asynchronous-workflows.md), e [expressões de computação](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4146c-125">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="using-function"></a><span data-ttu-id="4146c-126">usando a função</span><span class="sxs-lookup"><span data-stu-id="4146c-126">using Function</span></span>
<span data-ttu-id="4146c-127">O `using` função tem a seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4146c-127">The `using` function has the following form:</span></span>

<span data-ttu-id="4146c-128">`using`(*expression1*) *função ou lambda*</span><span class="sxs-lookup"><span data-stu-id="4146c-128">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="4146c-129">Em um `using` expressão, *expression1* cria o objeto deve ser descartado.</span><span class="sxs-lookup"><span data-stu-id="4146c-129">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="4146c-130">O resultado de *expression1* (o objeto deve ser descartado) torna-se um argumento, *valor*, *função ou lambda*, que é a uma função que espera um único restantes argumento de um tipo que corresponde ao valor produzido por *expression1*, ou uma expressão lambda que espera um argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="4146c-130">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="4146c-131">No final da execução da função, o tempo de execução chama `Dispose` e libera os recursos (a menos que o valor é `null`, caso em que a chamada Dispose não é realizada).</span><span class="sxs-lookup"><span data-stu-id="4146c-131">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="4146c-132">O exemplo a seguir demonstra o `using` expressão com uma expressão lambda.</span><span class="sxs-lookup"><span data-stu-id="4146c-132">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="4146c-133">A exemplo a seguir mostra o `using` expressão com uma função.</span><span class="sxs-lookup"><span data-stu-id="4146c-133">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="4146c-134">Observe que a função pode ser uma função que tem alguns argumentos já aplicados.</span><span class="sxs-lookup"><span data-stu-id="4146c-134">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="4146c-135">O exemplo de código a seguir demonstra isso.</span><span class="sxs-lookup"><span data-stu-id="4146c-135">The following code example demonstrates this.</span></span> <span data-ttu-id="4146c-136">Ele cria um arquivo que contém a cadeia de caracteres `XYZ`.</span><span class="sxs-lookup"><span data-stu-id="4146c-136">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="4146c-137">O `using` função e o `use` associação são praticamente equivalentes maneiras de realizar a mesma coisa.</span><span class="sxs-lookup"><span data-stu-id="4146c-137">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="4146c-138">O `using` palavra-chave fornece mais controle sobre quando `Dispose` é chamado.</span><span class="sxs-lookup"><span data-stu-id="4146c-138">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="4146c-139">Quando você usa `using`, `Dispose` é chamado no final da expressão lambda ou de função; quando você usar o `use` palavra-chave, `Dispose` é chamado no final do bloco de código.</span><span class="sxs-lookup"><span data-stu-id="4146c-139">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="4146c-140">Em geral, você deve preferir usar `use` em vez do `using` função.</span><span class="sxs-lookup"><span data-stu-id="4146c-140">In general, you should prefer to use `use` instead of the `using` function.</span></span>


## <a name="see-also"></a><span data-ttu-id="4146c-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4146c-141">See Also</span></span>
[<span data-ttu-id="4146c-142">Referência da Linguagem F#</span><span class="sxs-lookup"><span data-stu-id="4146c-142">F# Language Reference</span></span>](index.md)