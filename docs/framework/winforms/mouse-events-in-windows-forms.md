---
title: Eventos do mouse no Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 803f2daab5b8f6e216effe4a9ae9f34752d24e70
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="8565d-102">Eventos do mouse no Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8565d-102">Mouse Events in Windows Forms</span></span>
<span data-ttu-id="8565d-103">Quando manipula entradas de mouse, você geralmente deseja conhecer a localização do ponteiro do mouse e o estado dos botões do mouse.</span><span class="sxs-lookup"><span data-stu-id="8565d-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="8565d-104">Este tópico fornece detalhes sobre como obter essas informações de eventos do mouse e explica a ordem em que eventos de clique do mouse são gerados em controles dos Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8565d-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="8565d-105">Para obter uma lista e uma descrição de todos os eventos de mouse, consulte [Como a entrada do mouse funciona nos Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8565d-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="8565d-106">Consulte também [Visão geral de manipuladores de eventos (Windows Forms)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [Visão geral de eventos (Windows Forms)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="8565d-106">Also see [Event Handlers Overview (Windows Forms)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [Events Overview (Windows Forms)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\))</span></span>  
  
## <a name="mouse-information"></a><span data-ttu-id="8565d-107">Informações sobre o mouse</span><span class="sxs-lookup"><span data-stu-id="8565d-107">Mouse Information</span></span>  
 <span data-ttu-id="8565d-108">Um <xref:System.Windows.Forms.MouseEventArgs> é enviado aos manipuladores de eventos do mouse relacionados a clicar em um botão do mouse e rastrear seus movimentos.</span><span class="sxs-lookup"><span data-stu-id="8565d-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="8565d-109"><xref:System.Windows.Forms.MouseEventArgs>Fornece informações sobre o estado atual do mouse, incluindo a localização do ponteiro do mouse em coordenadas do cliente, quais botões são pressionados e se a roda do mouse foi rolado.</span><span class="sxs-lookup"><span data-stu-id="8565d-109"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="8565d-110">Muitos eventos do mouse, como aqueles que simplesmente avisam quando o ponteiro do mouse entrou ou saiu do limite de um controle, enviar um <xref:System.EventArgs> ao manipulador de eventos com nenhuma informação adicional.</span><span class="sxs-lookup"><span data-stu-id="8565d-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>  
  
 <span data-ttu-id="8565d-111">Se você deseja saber o estado atual dos botões do mouse ou o local do ponteiro do mouse e você quiser evitar manipular um evento de mouse, você também pode usar o <xref:System.Windows.Forms.Control.MouseButtons%2A> e <xref:System.Windows.Forms.Control.MousePosition%2A> propriedades da <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="8565d-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="8565d-112"><xref:System.Windows.Forms.Control.MouseButtons%2A>Retorna informações sobre quais botões são pressionados no momento.</span><span class="sxs-lookup"><span data-stu-id="8565d-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="8565d-113">O <xref:System.Windows.Forms.Control.MousePosition%2A> retorna as coordenadas de tela do ponteiro do mouse e é equivalente ao valor retornado por <xref:System.Windows.Forms.Cursor.Position%2A>.</span><span class="sxs-lookup"><span data-stu-id="8565d-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>  
  
## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="8565d-114">Convertendo entre coordenadas de cliente e da tela</span><span class="sxs-lookup"><span data-stu-id="8565d-114">Converting Between Screen and Client Coordinates</span></span>  
 <span data-ttu-id="8565d-115">Como algumas informações de localização do mouse estão em coordenadas de cliente e algumas estão em coordenadas de tela, talvez seja necessário converter um ponto de um sistema de coordenadas para outro.</span><span class="sxs-lookup"><span data-stu-id="8565d-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="8565d-116">Você pode fazer isso facilmente usando o <xref:System.Windows.Forms.Control.PointToClient%2A> e <xref:System.Windows.Forms.Control.PointToScreen%2A> métodos disponíveis no <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="8565d-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>  
  
## <a name="standard-click-event-behavior"></a><span data-ttu-id="8565d-117">Comportamento do evento de clique</span><span class="sxs-lookup"><span data-stu-id="8565d-117">Standard Click Event Behavior</span></span>  
 <span data-ttu-id="8565d-118">Se quiser manipular eventos de clique do mouse na ordem correta, você precisará conhecer a ordem em que os eventos de clique são gerados em controles dos Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8565d-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="8565d-119">Todos os controles dos Windows Forms geram eventos de clique na mesma ordem quando um botão do mouse é pressionado e liberado (independentemente de qual botão do mouse), exceto onde é indicado na lista a seguir de controles individuais.</span><span class="sxs-lookup"><span data-stu-id="8565d-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="8565d-120">A lista a seguir mostra a ordem dos eventos gerados por um único clique do botão do mouse:</span><span class="sxs-lookup"><span data-stu-id="8565d-120">The following list shows the order of events raised for a single mouse-button click:</span></span>  
  
1.  <span data-ttu-id="8565d-121"><xref:System.Windows.Forms.Control.MouseDown>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-121"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
2.  <span data-ttu-id="8565d-122"><xref:System.Windows.Forms.Control.Click>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-122"><xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
3.  <span data-ttu-id="8565d-123"><xref:System.Windows.Forms.Control.MouseClick>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-123"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>  
  
4.  <span data-ttu-id="8565d-124"><xref:System.Windows.Forms.Control.MouseUp>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-124"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 <span data-ttu-id="8565d-125">A seguir, temos a ordem dos eventos gerados por um clique duplo do botão do mouse:</span><span class="sxs-lookup"><span data-stu-id="8565d-125">Following is the order of events raised for a double mouse-button click:</span></span>  
  
1.  <span data-ttu-id="8565d-126"><xref:System.Windows.Forms.Control.MouseDown>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-126"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
2.  <span data-ttu-id="8565d-127"><xref:System.Windows.Forms.Control.Click>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-127"><xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
3.  <span data-ttu-id="8565d-128"><xref:System.Windows.Forms.Control.MouseClick>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-128"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>  
  
4.  <span data-ttu-id="8565d-129"><xref:System.Windows.Forms.Control.MouseUp>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-129"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
5.  <span data-ttu-id="8565d-130"><xref:System.Windows.Forms.Control.MouseDown>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-130"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
6.  <span data-ttu-id="8565d-131"><xref:System.Windows.Forms.Control.DoubleClick>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-131"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="8565d-132">(Isso pode variar, dependendo se o controle em questão tem o <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> bit de estilo definido para `true`.</span><span class="sxs-lookup"><span data-stu-id="8565d-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="8565d-133">Para obter mais informações sobre como definir um <xref:System.Windows.Forms.ControlStyles> bits, consulte o <xref:System.Windows.Forms.Control.SetStyle%2A> método.)</span><span class="sxs-lookup"><span data-stu-id="8565d-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>  
  
7.  <span data-ttu-id="8565d-134"><xref:System.Windows.Forms.Control.MouseDoubleClick>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>  
  
8.  <span data-ttu-id="8565d-135"><xref:System.Windows.Forms.Control.MouseUp>evento.</span><span class="sxs-lookup"><span data-stu-id="8565d-135"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 <span data-ttu-id="8565d-136">Para ver um exemplo de código que mostra a ordem dos eventos de clique do mouse, consulte [Como manipular eventos de entrada do usuário em controles dos Windows Forms](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="8565d-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>  
  
### <a name="individual-controls"></a><span data-ttu-id="8565d-137">Controles individuais</span><span class="sxs-lookup"><span data-stu-id="8565d-137">Individual Controls</span></span>  
 <span data-ttu-id="8565d-138">Os controles a seguir não estão em conformidade com o comportamento padrão dos eventos de clique do mouse:</span><span class="sxs-lookup"><span data-stu-id="8565d-138">The following controls do not conform to the standard mouse click event behavior:</span></span>  
  
-   <span data-ttu-id="8565d-139"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, e <xref:System.Windows.Forms.RadioButton> controles</span><span class="sxs-lookup"><span data-stu-id="8565d-139"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, and <xref:System.Windows.Forms.RadioButton> controls</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8565d-140">Para o <xref:System.Windows.Forms.ComboBox> controlar o comportamento dos eventos detalhado a seguir ocorre se o usuário clicar no campo de edição, o botão, ou em um item na lista.</span><span class="sxs-lookup"><span data-stu-id="8565d-140">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>  
  
    -   <span data-ttu-id="8565d-141">Com o botão esquerdo: <xref:System.Windows.Forms.Control.Click>,<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="8565d-141">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="8565d-142">Clique com botão direito do mouse: não são gerados eventos de clique</span><span class="sxs-lookup"><span data-stu-id="8565d-142">Right click: No click events raised</span></span>  
  
    -   <span data-ttu-id="8565d-143">Clique duas vezes à esquerda: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>,<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="8565d-143">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="8565d-144">Clique duas vezes com botão direito: não são gerados eventos de clique</span><span class="sxs-lookup"><span data-stu-id="8565d-144">Right double-click: No click events raised</span></span>  
  
-   <span data-ttu-id="8565d-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, e <xref:System.Windows.Forms.CheckedListBox> controles</span><span class="sxs-lookup"><span data-stu-id="8565d-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8565d-146">O comportamento do evento detalhado a seguir ocorre quando o usuário clica em qualquer lugar desses controles.</span><span class="sxs-lookup"><span data-stu-id="8565d-146">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>  
  
    -   <span data-ttu-id="8565d-147">Com o botão esquerdo: <xref:System.Windows.Forms.Control.Click>,<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="8565d-147">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="8565d-148">Clique com botão direito do mouse: não são gerados eventos de clique</span><span class="sxs-lookup"><span data-stu-id="8565d-148">Right click: No click events raised</span></span>  
  
    -   <span data-ttu-id="8565d-149">Clique duas vezes à esquerda: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>,<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="8565d-149">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
    -   <span data-ttu-id="8565d-150">Clique duas vezes com botão direito: não são gerados eventos de clique</span><span class="sxs-lookup"><span data-stu-id="8565d-150">Right double-click: No click events raised</span></span>  
  
-   <span data-ttu-id="8565d-151">Controle <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="8565d-151"><xref:System.Windows.Forms.ListView> control</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8565d-152">O comportamento dos eventos detalhado a seguir ocorre somente quando o usuário clica nos itens a <xref:System.Windows.Forms.ListView> controle.</span><span class="sxs-lookup"><span data-stu-id="8565d-152">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="8565d-153">Nenhum evento é gerado para cliques em qualquer outro lugar no controle.</span><span class="sxs-lookup"><span data-stu-id="8565d-153">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="8565d-154">Além dos eventos descritos mais adiante, há o <xref:System.Windows.Forms.ListView.BeforeLabelEdit> e <xref:System.Windows.Forms.ListView.AfterLabelEdit> eventos que podem ser de interesse para você, se você quiser usar a validação com o <xref:System.Windows.Forms.ListView> controle.</span><span class="sxs-lookup"><span data-stu-id="8565d-154">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    -   <span data-ttu-id="8565d-155">Com o botão esquerdo: <xref:System.Windows.Forms.Control.Click>,<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="8565d-155">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="8565d-156">Clique com botão direito: <xref:System.Windows.Forms.Control.Click>,<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="8565d-156">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="8565d-157">Clique duas vezes à esquerda: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="8565d-157">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
    -   <span data-ttu-id="8565d-158">À direita, clique duas vezes: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="8565d-158">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
-   <span data-ttu-id="8565d-159">Controle <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="8565d-159"><xref:System.Windows.Forms.TreeView> control</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8565d-160">O comportamento dos eventos detalhado a seguir ocorre somente quando o usuário clica nos próprios itens ou à direita dos itens no <xref:System.Windows.Forms.TreeView> controle.</span><span class="sxs-lookup"><span data-stu-id="8565d-160">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="8565d-161">Nenhum evento é gerado para cliques em qualquer outro lugar no controle.</span><span class="sxs-lookup"><span data-stu-id="8565d-161">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="8565d-162">Além dos descritos mais adiante, há o <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, e <xref:System.Windows.Forms.TreeView.AfterLabelEdit> eventos que podem ser de interesse para você, se você quiser usar a validação com o <xref:System.Windows.Forms.TreeView> controle .</span><span class="sxs-lookup"><span data-stu-id="8565d-162">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
    -   <span data-ttu-id="8565d-163">Com o botão esquerdo: <xref:System.Windows.Forms.Control.Click>,<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="8565d-163">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="8565d-164">Clique com botão direito: <xref:System.Windows.Forms.Control.Click>,<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="8565d-164">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="8565d-165">Clique duas vezes à esquerda: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="8565d-165">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
    -   <span data-ttu-id="8565d-166">À direita, clique duas vezes: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="8565d-166">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="8565d-167">Comportamento de pintura dos controles de alternância</span><span class="sxs-lookup"><span data-stu-id="8565d-167">Painting Behavior of Toggle Controls</span></span>  
 <span data-ttu-id="8565d-168">Alternar os controles, como os controles que derivam de <xref:System.Windows.Forms.ButtonBase> classe, tem o seguinte comportamento de pintura distinto em combinação com o mouse eventos de clique:</span><span class="sxs-lookup"><span data-stu-id="8565d-168">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>  
  
1.  <span data-ttu-id="8565d-169">O usuário pressiona o botão do mouse.</span><span class="sxs-lookup"><span data-stu-id="8565d-169">The user presses the mouse button.</span></span>  
  
2.  <span data-ttu-id="8565d-170">O controle pinta no estado pressionado.</span><span class="sxs-lookup"><span data-stu-id="8565d-170">The control paints in the pressed state.</span></span>  
  
3.  <span data-ttu-id="8565d-171">O <xref:System.Windows.Forms.Control.MouseDown> é gerado.</span><span class="sxs-lookup"><span data-stu-id="8565d-171">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>  
  
4.  <span data-ttu-id="8565d-172">O usuário libera o botão do mouse.</span><span class="sxs-lookup"><span data-stu-id="8565d-172">The user releases the mouse button.</span></span>  
  
5.  <span data-ttu-id="8565d-173">O controle pinta no estado elevado.</span><span class="sxs-lookup"><span data-stu-id="8565d-173">The control paints in the raised state.</span></span>  
  
6.  <span data-ttu-id="8565d-174">O <xref:System.Windows.Forms.Control.Click> é gerado.</span><span class="sxs-lookup"><span data-stu-id="8565d-174">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>  
  
7.  <span data-ttu-id="8565d-175">O <xref:System.Windows.Forms.Control.MouseClick> é gerado.</span><span class="sxs-lookup"><span data-stu-id="8565d-175">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>  
  
8.  <span data-ttu-id="8565d-176">O <xref:System.Windows.Forms.Control.MouseUp> é gerado.</span><span class="sxs-lookup"><span data-stu-id="8565d-176">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8565d-177">Se o usuário move o ponteiro fora do controle alternado enquanto o botão do mouse está inativo (como mover o mouse do <xref:System.Windows.Forms.Button> controlar enquanto ele está pressionado), o controle alternado se pintará no solto estado e somente o <xref:System.Windows.Forms.Control.MouseUp> evento ocorre.</span><span class="sxs-lookup"><span data-stu-id="8565d-177">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="8565d-178">O <xref:System.Windows.Forms.Control.Click> ou <xref:System.Windows.Forms.Control.MouseClick> eventos não ocorrerá nessa situação.</span><span class="sxs-lookup"><span data-stu-id="8565d-178">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8565d-179">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8565d-179">See Also</span></span>  
 [<span data-ttu-id="8565d-180">Entrada do mouse em um aplicativo dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8565d-180">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)