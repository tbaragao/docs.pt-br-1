---
title: "Introdução à tinta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc8ffe9ad68060d9dfbcafe99133a736237a2bb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started-with-ink"></a><span data-ttu-id="a47d0-102">Introdução à tinta</span><span class="sxs-lookup"><span data-stu-id="a47d0-102">Getting Started with Ink</span></span>
<span data-ttu-id="a47d0-103">Incorporar tinta digital a seus aplicativos ficou ainda mais fácil.</span><span class="sxs-lookup"><span data-stu-id="a47d0-103">Incorporating digital ink into your applications is easier than ever.</span></span> <span data-ttu-id="a47d0-104">A tinta evolui de ser corolário para os métodos de programação de COM e os Windows Forms para atingir integração total com o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-104">Ink has evolved from being a corollary to the COM and Windows Forms method of programming to achieving full integration into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="a47d0-105">Você não precisa instalar SDKs nem bibliotecas de tempo de execução separados.</span><span class="sxs-lookup"><span data-stu-id="a47d0-105">You do not need to install separate SDKs or runtime libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a47d0-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a47d0-106">Prerequisites</span></span>  
 <span data-ttu-id="a47d0-107">Para usar os exemplos a seguir, você deve primeiro instalar o Microsoft Visual Studio 2005 e o [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-107">To use the following examples, you must first install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="a47d0-108">Você também deve compreender como escrever aplicativos para o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-108">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="a47d0-109">Para obter mais informações sobre como começar com o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [passo a passo: meu primeiro aplicativo de área de trabalho do WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="a47d0-109">For more information about getting started with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="quick-start"></a><span data-ttu-id="a47d0-110">Início rápido</span><span class="sxs-lookup"><span data-stu-id="a47d0-110">Quick Start</span></span>  
 <span data-ttu-id="a47d0-111">Esta seção ajuda a escrever um aplicativo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] simples que coleta tinta.</span><span class="sxs-lookup"><span data-stu-id="a47d0-111">This section helps you write a simple [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that collects ink.</span></span>  
  
 <span data-ttu-id="a47d0-112">Se você ainda não tiver feito isso, instale o Microsoft Visual Studio 2005 e o [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-112">If you haven't already done so, install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="a47d0-113">Os aplicativos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geralmente devem ser compilados antes que você possa exibi-los, mesmo que consistem inteiramente em [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-113">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications usually must be compiled before you can view them, even if they consist entirely of [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="a47d0-114">No entanto, o [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] inclui um aplicativo, XamlPad, projetado para acelerar o processo de implementar uma interface do usuário baseada em [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-114">However, the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] includes an application, XamlPad, designed to speed up the process of implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-based UI.</span></span> <span data-ttu-id="a47d0-115">Você pode usar esse aplicativo para exibir e ajustar os primeiros exemplos neste documento.</span><span class="sxs-lookup"><span data-stu-id="a47d0-115">You can use that application to view and tinker with the first few samples in this document.</span></span> <span data-ttu-id="a47d0-116">O processo de criação de aplicativos compilados com base em [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] é abordado mais adiante neste documento.</span><span class="sxs-lookup"><span data-stu-id="a47d0-116">The process of creating compiled applications from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is covered later in this document.</span></span>  
  
 <span data-ttu-id="a47d0-117">Para inicializar XAMLPad, clique no menu **Iniciar**, aponte para **Todos os Programas**, para **SDK do Microsoft Windows** e para **Ferramentas** e clique em **XAMLPad**.</span><span class="sxs-lookup"><span data-stu-id="a47d0-117">To launch XAMLPad, click the **Start** menu, point to **All Programs**, point to **Microsoft Winndows SDK**, point to **Tools**, and click **XAMLPad**.</span></span> <span data-ttu-id="a47d0-118">No painel de renderização, XAMLPad processa o código XAML escrito no painel de código.</span><span class="sxs-lookup"><span data-stu-id="a47d0-118">In the rendering pane, XAMLPad renders the XAML code written in the code pane.</span></span> <span data-ttu-id="a47d0-119">Você pode editar o código XAML e as alterações imediatamente aparecerão no painel de renderização.</span><span class="sxs-lookup"><span data-stu-id="a47d0-119">You can edit the XAML code, and the changes immediately appear in the rendering pane.</span></span>  
  
#### <a name="got-ink"></a><span data-ttu-id="a47d0-120">Tem tinta?</span><span class="sxs-lookup"><span data-stu-id="a47d0-120">Got Ink?</span></span>  
 <span data-ttu-id="a47d0-121">Para iniciar seu primeiro aplicativo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que dê suporte a tinta:</span><span class="sxs-lookup"><span data-stu-id="a47d0-121">To start your first [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that supports ink:</span></span>  
  
1.  <span data-ttu-id="a47d0-122">Abra o Microsoft Visual Studio 2005</span><span class="sxs-lookup"><span data-stu-id="a47d0-122">Open Microsoft Visual Studio 2005</span></span>  
  
2.  <span data-ttu-id="a47d0-123">Criar novos **Aplicativos do Windows (WPF)**</span><span class="sxs-lookup"><span data-stu-id="a47d0-123">Create a new **Windows Application (WPF)**</span></span>  
  
3.  <span data-ttu-id="a47d0-124">Digite `<InkCanvas/>` entre as marcas `<Grid>`</span><span class="sxs-lookup"><span data-stu-id="a47d0-124">Type `<InkCanvas/>` between the `<Grid>` tags</span></span>  
  
4.  <span data-ttu-id="a47d0-125">Pressione **F5** para inicializar o aplicativo no depurador</span><span class="sxs-lookup"><span data-stu-id="a47d0-125">Press **F5** to launch your application in the debugger</span></span>  
  
5.  <span data-ttu-id="a47d0-126">Usando uma caneta ou o mouse, escreva **Olá, Mundo** na janela</span><span class="sxs-lookup"><span data-stu-id="a47d0-126">Using a stylus or mouse, write **hello world** in the window</span></span>  
  
 <span data-ttu-id="a47d0-127">Você escreveu o equivalente em tinta de um aplicativo "Olá, Mundo" com apenas 12 pressionamentos de tecla!</span><span class="sxs-lookup"><span data-stu-id="a47d0-127">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>  
  
#### <a name="spice-up-your-application"></a><span data-ttu-id="a47d0-128">Aprimore seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="a47d0-128">Spice Up Your Application</span></span>  
 <span data-ttu-id="a47d0-129">Vamos aproveitar alguns recursos do [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-129">Let’s take advantage of some features of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  <span data-ttu-id="a47d0-130">Substitua tudo entre as marcas de abertura \<Window> e fechamento \</Window> marcas com a marcação a seguir para obter uma tela de fundo de pincel de gradiente na superfície de tinta.</span><span class="sxs-lookup"><span data-stu-id="a47d0-130">Replace everything between the opening \<Window> and closing \</Window> tags with the following markup to get a gradient brush background on your inking surface.</span></span>  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a><span data-ttu-id="a47d0-131">Usando animação</span><span class="sxs-lookup"><span data-stu-id="a47d0-131">Using Animation</span></span>  
 <span data-ttu-id="a47d0-132">Por diversão, vamos animar as cores do pincel do gradiente.</span><span class="sxs-lookup"><span data-stu-id="a47d0-132">For fun, let's animate the colors of the gradient brush.</span></span> <span data-ttu-id="a47d0-133">Adicione o seguinte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] após a marca `</InkCanvas>` de fechamento, mas antes da marca `</Page>` de fechamento.</span><span class="sxs-lookup"><span data-stu-id="a47d0-133">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] after the closing `</InkCanvas>` tag but before the closing `</Page>` tag.</span></span>  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a><span data-ttu-id="a47d0-134">Adicionando algum código por trás de XAML</span><span class="sxs-lookup"><span data-stu-id="a47d0-134">Adding Some Code Behind the XAML</span></span>  
 <span data-ttu-id="a47d0-135">Embora XAML torne muito fácil projetar a interface do usuário, qualquer aplicativo do mundo real precisa adicionar código para manipular eventos.</span><span class="sxs-lookup"><span data-stu-id="a47d0-135">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="a47d0-136">Aqui está um exemplo simples que ampliará a tinta em resposta a um clique com o botão direito do mouse:</span><span class="sxs-lookup"><span data-stu-id="a47d0-136">Here is a simple example that zooms in on the ink in response to a right-click from a mouse:</span></span>  
  
 <span data-ttu-id="a47d0-137">Definir o manipulador `MouseRightButtonUp` no seu [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a47d0-137">Set the `MouseRightButtonUp` handler in your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span></span>  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 <span data-ttu-id="a47d0-138">No Gerenciador de Soluções do Visual Studio, expanda Windows1.xaml e abra o arquivo code-behind, Window1.xaml.cs ou Window1.xaml.vb, se você estiver usando Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a47d0-138">In Visual Studio’s Solution Explorer, expand Windows1.xaml and open the code-behind file, Window1.xaml.cs or Window1.xaml.vb if you are using Visual Basic.</span></span> <span data-ttu-id="a47d0-139">Adicione o seguinte código do manipulador de eventos:</span><span class="sxs-lookup"><span data-stu-id="a47d0-139">Add the following event handler code:</span></span>  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 <span data-ttu-id="a47d0-140">Agora execute seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a47d0-140">Now, run your application.</span></span> <span data-ttu-id="a47d0-141">Adicione alguma tinta e clique com o botão direito do mouse ou execute uma ação de pressionar e segurar equivalente com uma caneta.</span><span class="sxs-lookup"><span data-stu-id="a47d0-141">Add some ink and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>  
  
#### <a name="using-procedural-code-instead-of-xaml"></a><span data-ttu-id="a47d0-142">Usando código de procedimento, em vez de XAML</span><span class="sxs-lookup"><span data-stu-id="a47d0-142">Using Procedural Code Instead of XAML</span></span>  
 <span data-ttu-id="a47d0-143">Você pode acessar todos os recursos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] do código de procedimento.</span><span class="sxs-lookup"><span data-stu-id="a47d0-143">You can access all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features from procedural code.</span></span> <span data-ttu-id="a47d0-144">Aqui está um aplicativo "Olá, Mundo da Tinta" para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que não usa nenhum [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a47d0-144">Here is a "Hello Ink World" application for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] that doesn’t use any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] at all.</span></span> <span data-ttu-id="a47d0-145">Cole o código abaixo em um Aplicativo de Console vazio no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a47d0-145">Paste the code below into an empty Console Application in Visual Studio.</span></span> <span data-ttu-id="a47d0-146">Adicione referências aos assemblies PresentationCore, PresentationFramework e WindowsBase e compile o aplicativo pressionando **F5**:</span><span class="sxs-lookup"><span data-stu-id="a47d0-146">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies, and build the application by pressing **F5**:</span></span>  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a47d0-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a47d0-147">See Also</span></span>  
 [<span data-ttu-id="a47d0-148">Tinta digital</span><span class="sxs-lookup"><span data-stu-id="a47d0-148">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [<span data-ttu-id="a47d0-149">Coletando tinta</span><span class="sxs-lookup"><span data-stu-id="a47d0-149">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [<span data-ttu-id="a47d0-150">Reconhecimento de manuscrito</span><span class="sxs-lookup"><span data-stu-id="a47d0-150">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [<span data-ttu-id="a47d0-151">Armazenando a tinta</span><span class="sxs-lookup"><span data-stu-id="a47d0-151">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)