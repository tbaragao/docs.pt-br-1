---
title: "Como criar um suplemento que seja uma interface do usuário"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9151dd5fa36e3691361bcf6d7c7b281646982f3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a><span data-ttu-id="b777c-102">Como criar um suplemento que seja uma interface do usuário</span><span class="sxs-lookup"><span data-stu-id="b777c-102">How to: Create an Add-In That Is a UI</span></span>
<span data-ttu-id="b777c-103">Este exemplo mostra como criar um suplemento que é um [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que é hospedado por um [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicativo autônomo.</span><span class="sxs-lookup"><span data-stu-id="b777c-103">This example shows how to create an add-in that is a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)][!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] which is hosted by a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application.</span></span>  
  
 <span data-ttu-id="b777c-104">O suplemento é um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que é um [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] controle de usuário.</span><span class="sxs-lookup"><span data-stu-id="b777c-104">The add-in is a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that is a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] user control.</span></span> <span data-ttu-id="b777c-105">O conteúdo do controle de usuário é um único botão que, quando clicado, exibe uma caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="b777c-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="b777c-106">O [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicativo autônomo hospeda o suplemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] como o conteúdo da janela principal do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b777c-106">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application hosts the add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] as the content of the main application window.</span></span>  
  
 <span data-ttu-id="b777c-107">**Pré-requisitos**</span><span class="sxs-lookup"><span data-stu-id="b777c-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="b777c-108">Este exemplo realça o [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensões para o [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] adicionar no modelo de habilitar esse cenário e assume o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b777c-108">This example highlights the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model that enable this scenario, and assumes the following:</span></span>  
  
-   <span data-ttu-id="b777c-109">Conhecimento sobre o [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] adicionar no modelo, incluindo o pipeline de suplemento e desenvolvimento de host.</span><span class="sxs-lookup"><span data-stu-id="b777c-109">Knowledge of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="b777c-110">Se você estiver familiarizado com esses conceitos, consulte [suplementos e extensibilidade](../../../../docs/framework/add-ins/index.md).</span><span class="sxs-lookup"><span data-stu-id="b777c-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](../../../../docs/framework/add-ins/index.md).</span></span> <span data-ttu-id="b777c-111">Para obter um tutorial que demonstra a implementação de um pipeline, um suplemento e um aplicativo host, consulte [passo a passo: Criando um aplicativo extensível](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span><span class="sxs-lookup"><span data-stu-id="b777c-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
-   <span data-ttu-id="b777c-112">Conhecimento do [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensões para o [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] adicionar no modelo, que pode ser encontrado aqui: [visão geral de suplementos WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b777c-112">Knowledge of the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, which can be found here:     [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b777c-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b777c-113">Example</span></span>  
 <span data-ttu-id="b777c-114">Para criar um suplemento que é um [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requer código específico para cada segmento de pipeline, o suplemento e o aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="b777c-114">To create an add-in that is a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="b777c-115">Implementando o segmento de pipeline de contrato</span><span class="sxs-lookup"><span data-stu-id="b777c-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="b777c-116">Quando um suplemento é um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], o contrato para o suplemento deve implementar <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="b777c-116">When an add-in is a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], the contract for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="b777c-117">No exemplo, `IWPFAddInContract` implementa <xref:System.AddIn.Contract.INativeHandleContract>, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b777c-117">In the example, `IWPFAddInContract` implements <xref:System.AddIn.Contract.INativeHandleContract>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="b777c-118">Implementando o segmento de pipeline de exibição de suplemento</span><span class="sxs-lookup"><span data-stu-id="b777c-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="b777c-119">Como o suplemento é implementado como uma subclasse do <xref:System.Windows.FrameworkElement> tipo, o modo de exibição também deve subclasse <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="b777c-119">Because the add-in is implemented as a subclass of the <xref:System.Windows.FrameworkElement> type, the add-in view must also subclass <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b777c-120">O código a seguir mostra a exibição do suplemento do contrato, implementado como o `WPFAddInView` classe.</span><span class="sxs-lookup"><span data-stu-id="b777c-120">The following code shows the add-in view of the contract, implemented as the `WPFAddInView` class.</span></span>  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 <span data-ttu-id="b777c-121">Aqui, o modo de exibição é derivado de <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="b777c-121">Here, the add-in view is derived from <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="b777c-122">Consequentemente, o suplemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] também deve derivar de <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="b777c-122">Consequently, the add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] should also derive from <xref:System.Windows.Controls.UserControl>.</span></span>  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="b777c-123">Implementando o segmento de pipeline do adaptador no lado do suplemento</span><span class="sxs-lookup"><span data-stu-id="b777c-123">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="b777c-124">Enquanto o contrato é um <xref:System.AddIn.Contract.INativeHandleContract>, o suplemento é um <xref:System.Windows.FrameworkElement> (conforme especificado pelo segmento de pipeline de suplemento do modo de exibição).</span><span class="sxs-lookup"><span data-stu-id="b777c-124">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the add-in is a <xref:System.Windows.FrameworkElement> (as specified by the add-in view pipeline segment).</span></span> <span data-ttu-id="b777c-125">Portanto, o <xref:System.Windows.FrameworkElement> devem ser convertidos para um <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar o limite de isolamento.</span><span class="sxs-lookup"><span data-stu-id="b777c-125">Therefore, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="b777c-126">O trabalho é executado pelo adaptador do lado do suplemento chamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b777c-126">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 <span data-ttu-id="b777c-127">No suplemento do modelo em que um suplemento retorna um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (consulte [criar um suplemento que retorna uma interface de usuário](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), o adaptador de suplemento converte o <xref:System.Windows.FrameworkElement> para um <xref:System.AddIn.Contract.INativeHandleContract> chamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b777c-127">In the add-in model where an add-in returns a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (see [Create an Add-In That Returns a UI](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), the add-in adapter converted the <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="b777c-128"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>também deve ser chamado nesse modelo, embora você precise implementar um método do qual gravar o código para chamá-lo.</span><span class="sxs-lookup"><span data-stu-id="b777c-128"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> must also be called in this model, although you need to implement a method from which to write the code to call it.</span></span> <span data-ttu-id="b777c-129">Você pode fazer isso por meio da substituição <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> e implementar o código que chama <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> se o código que está chamando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> está esperando um <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="b777c-129">You do this by overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> and implementing the code that calls <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> if the code that is calling <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is expecting an <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="b777c-130">Nesse caso, o chamador será o adaptador do lado do host, que é abordado em uma seção mais adiante.</span><span class="sxs-lookup"><span data-stu-id="b777c-130">In this case, the caller will be the host-side adapter, which is covered in a subsequent subsection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b777c-131">Você também precisa substituir <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> nesse modelo para habilitar tabulações entre aplicativo host [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] e suplemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b777c-131">You also need to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in this model to enable tabbing between host application [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] and add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> <span data-ttu-id="b777c-132">Para obter mais informações, consulte "Adicionar limitações de WPF" [visão geral de suplementos WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b777c-132">For more information, see "WPF Add-In Limitations" in [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span></span>  
  
 <span data-ttu-id="b777c-133">Como o adaptador do lado do suplemento implementa uma interface que deriva de <xref:System.AddIn.Contract.INativeHandleContract>, você também precisa implementar <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, embora isso seja ignorado quando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> é substituído.</span><span class="sxs-lookup"><span data-stu-id="b777c-133">Because the add-in-side adapter implements an interface that derives from <xref:System.AddIn.Contract.INativeHandleContract>, you also need to implement <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, although this is ignored when <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is overridden.</span></span>  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="b777c-134">Implementando o segmento de pipeline de exibição de host</span><span class="sxs-lookup"><span data-stu-id="b777c-134">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="b777c-135">Nesse modelo, o aplicativo host tipicamente espera que o modo de host para ser um <xref:System.Windows.FrameworkElement> subclasse.</span><span class="sxs-lookup"><span data-stu-id="b777c-135">In this model, the host application typically expects the host view to be a <xref:System.Windows.FrameworkElement> subclass.</span></span> <span data-ttu-id="b777c-136">O adaptador do lado do host deve converter o <xref:System.AddIn.Contract.INativeHandleContract> para um <xref:System.Windows.FrameworkElement> depois que o <xref:System.AddIn.Contract.INativeHandleContract> cruzar o limite de isolamento.</span><span class="sxs-lookup"><span data-stu-id="b777c-136">The host-side adapter must convert the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary.</span></span> <span data-ttu-id="b777c-137">Como um método não está sendo chamado pelo aplicativo host para obter o <xref:System.Windows.FrameworkElement>, o modo de host deve "retornar" o <xref:System.Windows.FrameworkElement> por que o contém.</span><span class="sxs-lookup"><span data-stu-id="b777c-137">Because a method isn't being called by the host application to get the <xref:System.Windows.FrameworkElement>, the host view must "return" the <xref:System.Windows.FrameworkElement> by containing it.</span></span> <span data-ttu-id="b777c-138">Consequentemente, o modo de host deve derivar de uma subclasse de <xref:System.Windows.FrameworkElement> que pode conter outros [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], como <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="b777c-138">Consequently, the host view must derive from a subclass of <xref:System.Windows.FrameworkElement> that can contain other [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], such as <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="b777c-139">O código a seguir mostra a exibição de host do contrato, implementado como o `WPFAddInHostView` classe.</span><span class="sxs-lookup"><span data-stu-id="b777c-139">The following code shows the host view of the contract, implemented as the `WPFAddInHostView` class.</span></span>  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="b777c-140">Implementando o segmento de pipeline do adaptador no lado do host</span><span class="sxs-lookup"><span data-stu-id="b777c-140">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="b777c-141">Enquanto o contrato é um <xref:System.AddIn.Contract.INativeHandleContract>, o aplicativo de host espera um <xref:System.Windows.Controls.UserControl> (como especificado pelo modo de host).</span><span class="sxs-lookup"><span data-stu-id="b777c-141">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the host application expects a <xref:System.Windows.Controls.UserControl> (as specified by the host view).</span></span> <span data-ttu-id="b777c-142">Consequentemente, o <xref:System.AddIn.Contract.INativeHandleContract> deve ser convertido em um <xref:System.Windows.FrameworkElement> após cruzar o limite de isolamento, antes de ser definido como conteúdo da exibição de host (que é derivado de <xref:System.Windows.Controls.UserControl>).</span><span class="sxs-lookup"><span data-stu-id="b777c-142">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary, before being set as content of the host view (which derives from <xref:System.Windows.Controls.UserControl>).</span></span>  
  
 <span data-ttu-id="b777c-143">O trabalho é executado pelo adaptador no lado do host, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b777c-143">This work is performed by the host-side adapter, as shown in the following code.</span></span>  
  
  
  
 <span data-ttu-id="b777c-144">Como você pode ver, o adaptador do lado do host adquire o <xref:System.AddIn.Contract.INativeHandleContract> chamando o adaptador do lado do suplemento <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> método (Este é o ponto em que o <xref:System.AddIn.Contract.INativeHandleContract> cruzar o limite de isolamento).</span><span class="sxs-lookup"><span data-stu-id="b777c-144">As you can see, the host-side adapter acquires the <xref:System.AddIn.Contract.INativeHandleContract> by calling the add-in-side adapter's <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> method (this is the point where the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary).</span></span>  
  
 <span data-ttu-id="b777c-145">O adaptador do lado do host converte o <xref:System.AddIn.Contract.INativeHandleContract> para um <xref:System.Windows.FrameworkElement> chamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b777c-145">The host-side adapter then converts the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="b777c-146">Por fim, o <xref:System.Windows.FrameworkElement> é definido como o conteúdo da exibição do host.</span><span class="sxs-lookup"><span data-stu-id="b777c-146">Finally, the <xref:System.Windows.FrameworkElement> is set as the content of the host view.</span></span>  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="b777c-147">Implementando os suplementos</span><span class="sxs-lookup"><span data-stu-id="b777c-147">Implementing the Add-In</span></span>  
 <span data-ttu-id="b777c-148">Com o adaptador no lado do suplemento e a exibição de suplemento em vigor, o suplemento pode ser implementado derivando da exibição de suplemento, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b777c-148">With the add-in-side adapter and add-in view in place, the add-in can be implemented by deriving from the add-in view, as shown in the following code.</span></span>  
  
  
  
  
  
 <span data-ttu-id="b777c-149">Neste exemplo, você pode ver um benefício interessante desse modelo: os desenvolvedores suplemento só precisam implementar o suplemento (já que é o [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] também), em vez de uma classe do suplemento e um suplemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b777c-149">From this example, you can see one interesting benefit of this model: add-in developers only need to implement the add-in (since it is the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] as well), rather than both an add-in class and an add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="b777c-150">Implementando o aplicativo host</span><span class="sxs-lookup"><span data-stu-id="b777c-150">Implementing the Host Application</span></span>  
 <span data-ttu-id="b777c-151">Com o adaptador do lado do host e o modo de host criados, o aplicativo de host pode usar o [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de suplemento para abrir a pipeline e adquirir um modo de host do suplemento.</span><span class="sxs-lookup"><span data-stu-id="b777c-151">With the host-side adapter and host view created, the host application can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model to open the pipeline and acquire a host view of the add-in.</span></span> <span data-ttu-id="b777c-152">Essas etapas são mostradas no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b777c-152">These steps are shown in the following code.</span></span>  
  
  
  
 <span data-ttu-id="b777c-153">O aplicativo host utiliza típico [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] código de modelo de suplemento para ativar o suplemento, que implicitamente retorna o modo de host para o aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="b777c-153">The host application uses typical [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model code to activate the add-in, which implicitly returns the host view to the host application.</span></span> <span data-ttu-id="b777c-154">O aplicativo host subsequentemente exibe o modo de host (que é um <xref:System.Windows.Controls.UserControl>) de um <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="b777c-154">The host application subsequently displays the host view (which is a <xref:System.Windows.Controls.UserControl>) from a <xref:System.Windows.Controls.Grid>.</span></span>  
  
 <span data-ttu-id="b777c-155">O código para processar interações com o suplemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] é executado no domínio de aplicativo do suplemento.</span><span class="sxs-lookup"><span data-stu-id="b777c-155">The code for processing interactions with the add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] runs in the add-in's application domain.</span></span> <span data-ttu-id="b777c-156">Essas ações incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b777c-156">These interactions include the following:</span></span>  
  
-   <span data-ttu-id="b777c-157">Tratamento de <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="b777c-157">Handling the <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
-   <span data-ttu-id="b777c-158">Mostrando o <xref:System.Windows.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="b777c-158">Showing the <xref:System.Windows.MessageBox>.</span></span>  
  
 <span data-ttu-id="b777c-159">Esta atividade é completamente isolada do aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="b777c-159">This activity is completely isolated from the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b777c-160">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b777c-160">See Also</span></span>  
 [<span data-ttu-id="b777c-161">Suplementos e extensibilidade</span><span class="sxs-lookup"><span data-stu-id="b777c-161">Add-ins and Extensibility</span></span>](../../../../docs/framework/add-ins/index.md)  
 [<span data-ttu-id="b777c-162">Visão geral dos suplementos do WPF</span><span class="sxs-lookup"><span data-stu-id="b777c-162">WPF Add-Ins Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)