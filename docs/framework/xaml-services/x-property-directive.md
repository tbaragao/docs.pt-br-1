---
title: Diretiva x:Property
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
caps.latest.revision: "6"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a59eb23ab3ed6ee6adbbebab0859caffd293b24f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="xproperty-directive"></a><span data-ttu-id="00e48-102">Diretiva x:Property</span><span class="sxs-lookup"><span data-stu-id="00e48-102">x:Property Directive</span></span>
<span data-ttu-id="00e48-103">Declara uma propriedade XAML na marcação.</span><span class="sxs-lookup"><span data-stu-id="00e48-103">Declares a XAML property in markup.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="00e48-104">Uso de elemento Object do XAML</span><span class="sxs-lookup"><span data-stu-id="00e48-104">XAML Object Element Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Property Name="propertyName" Type="propertyType/>  
    additionalProperties  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="00e48-105">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="00e48-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="00e48-106">Nome da classe de backup ou classe parcial para a produção de XAML.</span><span class="sxs-lookup"><span data-stu-id="00e48-106">Name of the backing class or partial class for the XAML production.</span></span>|  
|`propertyName`|<span data-ttu-id="00e48-107">Nome da propriedade que está sendo definida.</span><span class="sxs-lookup"><span data-stu-id="00e48-107">Member name of the property being defined.</span></span>|  
|`propertyType`|<span data-ttu-id="00e48-108">Digite um nome (ou outro formato de cadeia de caracteres, específica da estrutura) que especifica o tipo desta propriedade.</span><span class="sxs-lookup"><span data-stu-id="00e48-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00e48-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="00e48-109">Remarks</span></span>  
 <span data-ttu-id="00e48-110">Na implementação de serviços XAML do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00e48-110">In the .NET Framework XAML Services implementation, .</span></span> <span data-ttu-id="00e48-111">`x:Property`não tem um tipo direto fazendo, mas há suporte para o <xref:System.Windows.Markup.PropertyDefinition> classe.</span><span class="sxs-lookup"><span data-stu-id="00e48-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="00e48-112">Em um fluxo do nó XAML, uma `x:Property` elemento é representado como um membro chamado `Property`, do namespace XAML de linguagem XAML.</span><span class="sxs-lookup"><span data-stu-id="00e48-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="00e48-113">O membro `Property` conter atributos como declarado pela marcação.</span><span class="sxs-lookup"><span data-stu-id="00e48-113">The member `Property` hold attributes as declared by markup.</span></span>  
  
 <span data-ttu-id="00e48-114">O significado de `Name` e `Type` não são atribuídos no nível de serviços XAML do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00e48-114">The meaning of `Name` and `Type` are not assigned at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="00e48-115">Eles são armazenados no fluxo do nó XAML inicial como valores de cadeia de caracteres, deve ser interpretado posteriormente com as regras que podem ser impostas por estruturas específicas.</span><span class="sxs-lookup"><span data-stu-id="00e48-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="00e48-116">O significado pode alinhar um nome XAML e o tipo XAML que significa ou somente pode ser válido em um sistema de tipo de backup, dependendo da implementação.</span><span class="sxs-lookup"><span data-stu-id="00e48-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>  
  
 <span data-ttu-id="00e48-117">Para dar suporte a um uso prático de `x:Members` como um meio para especificar definições de membro na marcação, os membros devem ser associados uma classe que pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="00e48-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="00e48-118">O modelo desejado é que `x:Members` existe como um membro de um tipo que especifica um `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="00e48-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="00e48-119">No entanto, o mecanismo para a associação de tipos e membros ou para a produção de definições de membro dinâmico não tem suporte no nível de serviços XAML do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00e48-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="00e48-120">Isso é da esquerda para estruturas individuais que têm modelos de aplicativos que dão suporte a definições de membro de XAML.</span><span class="sxs-lookup"><span data-stu-id="00e48-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="00e48-121">Normalmente, as ações de compilação MSBUILD que a compilação de marcação XAML e um integração-lo com code-behind ou produzir somente de XAML assemblies são necessários para dar suporte a esse recurso.</span><span class="sxs-lookup"><span data-stu-id="00e48-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="00e48-122">Propriedade x: para Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="00e48-122">x:Property for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="00e48-123">Para Windows Workflow Foundation, `x:Property` define os membros de uma atividade personalizada composta inteiramente em XAML ou XAML – definido membros dinâmicos para um designer de atividade com code-behind.</span><span class="sxs-lookup"><span data-stu-id="00e48-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="00e48-124">`x:Class`também deve ser especificado no elemento raiz da produção XAML.</span><span class="sxs-lookup"><span data-stu-id="00e48-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="00e48-125">Isso não é um requisito no nível de serviços XAML do .NET Framework, mas se torna um requisito quando a produção de XAML é carregada pelas ações de compilação do MSBUILD que dão suporte a atividades personalizadas e XAML do Windows Workflow Foundation em geral.</span><span class="sxs-lookup"><span data-stu-id="00e48-125">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="00e48-126">O Windows Workflow Foundation não usa o nome de tipo XAML puro como seu valor desejado para o `x:Property` `Type` de atributo e, em vez disso, usa uma convenção de que não está documentada aqui.</span><span class="sxs-lookup"><span data-stu-id="00e48-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="00e48-127">Para obter mais informações, consulte [criação dinâmica de atividade](http://msdn.microsoft.com/library/dd807392.aspx).</span><span class="sxs-lookup"><span data-stu-id="00e48-127">For more information, see [Dynamic Activity Creation](http://msdn.microsoft.com/library/dd807392.aspx).</span></span>