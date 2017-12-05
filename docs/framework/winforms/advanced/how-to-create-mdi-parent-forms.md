---
title: "Como criar formulários pai MDI"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f768e01981f75e5e322fd984e73ccf7b185c5e20
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="0ddd8-102">Como criar formulários pai MDI</span><span class="sxs-lookup"><span data-stu-id="0ddd8-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="0ddd8-103">Este tópico usa o controle <xref:System.Windows.Forms.MainMenu>, que foi substituído pelo controle <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="0ddd8-104">O controle <xref:System.Windows.Forms.MainMenu> é mantido para compatibilidade com versões anteriores e uso futuro, se você desejar.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="0ddd8-105">Para obter informações sobre como criar um MDI pai formulário usando um <xref:System.Windows.Forms.MenuStrip>, consulte [como: criar uma lista de janelas MDI com MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0ddd8-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="0ddd8-106">A base de um aplicativo de interface MDI é o formulário MDI pai.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="0ddd8-107">Este é o formulário que contém as janelas MDI filhas, que as subjanelas nas quais o usuário interage com o aplicativo MDI.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="0ddd8-108">Criar um formulário MDI pai é fácil, tanto no Designer de Formulários do Windows e por meio de programação.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="0ddd8-109">Para criar um formulário MDI pai no tempo de design</span><span class="sxs-lookup"><span data-stu-id="0ddd8-109">To create an MDI parent form at design time</span></span>  
  
1.  <span data-ttu-id="0ddd8-110">Criar um projeto de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-110">Create a Windows Application project.</span></span>  
  
2.  <span data-ttu-id="0ddd8-111">No **propriedades** janela, defina o <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propriedade **true**.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="0ddd8-112">Isso designa o formulário como um recipiente MDI para janelas filho.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ddd8-113">Ao configurar propriedades na janela **Propriedades**, você também pode definir a propriedade `WindowState` para **Maximized**, se desejar, pois é mais fácil manipular janelas filho MDI quando o formulário pai está maximizado.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="0ddd8-114">Além disso, esteja ciente de que a borda do formulário MDI pai selecionará a cor do sistema (definida no Painel de Controle do Sistema do Windows), em vez da cor de fundo definida usando a propriedade <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3.  <span data-ttu-id="0ddd8-115">Na **Caixa de Ferramentas**, arraste um controle **MenuStrip** para o formulário.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="0ddd8-116">Crie um item de menu de nível superior com a propriedade **Text** definida para **&File** com itens de submenu chamados **&New** e **&Close**.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="0ddd8-117">Crie também um item de menu de nível superior chamado **&Window**.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="0ddd8-118">O primeiro menu criará e ocultará itens do menu no tempo de execução e o segundo menu irá controlar as janelas MDI filhas abertas.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="0ddd8-119">Neste ponto, você já terá criado uma janela MDI pai.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-119">At this point, you have created an MDI parent window.</span></span>  
  
4.  <span data-ttu-id="0ddd8-120">Pressione **F5** para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0ddd8-120">Press **F5** to run the application.</span></span> <span data-ttu-id="0ddd8-121">Para obter informações sobre como criar janelas filho MDI que operam no formulário pai MDI, confira [Como criar formulários filho MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0ddd8-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddd8-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0ddd8-122">See Also</span></span>  
 [<span data-ttu-id="0ddd8-123">Aplicativos da interface MDI (Interface de Vários Documentos)</span><span class="sxs-lookup"><span data-stu-id="0ddd8-123">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="0ddd8-124">Como criar formulários filho MDI</span><span class="sxs-lookup"><span data-stu-id="0ddd8-124">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="0ddd8-125">Como determinar o filho MDI ativo</span><span class="sxs-lookup"><span data-stu-id="0ddd8-125">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="0ddd8-126">Como Enviar Dados para o Filho MDI Ativo</span><span class="sxs-lookup"><span data-stu-id="0ddd8-126">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="0ddd8-127">Como Organizar Formulários Filho MDI</span><span class="sxs-lookup"><span data-stu-id="0ddd8-127">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)