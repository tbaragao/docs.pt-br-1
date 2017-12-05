---
title: "Visão geral do controle RichTextBox (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4278f569a789ca6e8466e0b8e71557446b63955e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="richtextbox-control-overview-windows-forms"></a><span data-ttu-id="e5404-102">Visão geral do controle RichTextBox (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e5404-102">RichTextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="e5404-103">O controle <xref:System.Windows.Forms.RichTextBox> dos Windows Forms é usado para exibir, inserir e manipular texto com formatação.</span><span class="sxs-lookup"><span data-stu-id="e5404-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="e5404-104">O <xref:System.Windows.Forms.RichTextBox> controle faz tudo o que o <xref:System.Windows.Forms.TextBox> do controle, mas ele também pode exibir fontes, cores e links; carregar texto e imagens inseridas de um arquivo; e localizar os caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="e5404-104">The <xref:System.Windows.Forms.RichTextBox> control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; and find specified characters.</span></span> <span data-ttu-id="e5404-105">O controle <xref:System.Windows.Forms.RichTextBox> normalmente é usado para fornecer manipulação de texto e exibir recursos semelhantes aos aplicativos de processamento de texto como o Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="e5404-105">The <xref:System.Windows.Forms.RichTextBox> control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="e5404-106">Como o <xref:System.Windows.Forms.TextBox> controle, o <xref:System.Windows.Forms.RichTextBox> controle pode exibir barras de rolagem; mas ao contrário de <xref:System.Windows.Forms.TextBox> controle, sua configuração padrão é exibir barras de rolagem horizontais e verticais conforme necessário e traz configurações de barra de rolagem adicionais.</span><span class="sxs-lookup"><span data-stu-id="e5404-106">Like the <xref:System.Windows.Forms.TextBox> control, the <xref:System.Windows.Forms.RichTextBox> control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, its default setting is to display both horizontal and vertical scrollbars as needed, and it has additional scrollbar settings.</span></span>  
  
## <a name="working-with-the-richtextbox-control"></a><span data-ttu-id="e5404-107">Trabalhando com o controle RichTextBox</span><span class="sxs-lookup"><span data-stu-id="e5404-107">Working with the RichTextBox Control</span></span>  
 <span data-ttu-id="e5404-108">Assim como acontece com o <xref:System.Windows.Forms.TextBox> controle, o texto exibido é definido pelo <xref:System.Windows.Forms.RichTextBox.Text%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="e5404-108">As with the <xref:System.Windows.Forms.TextBox> control, the text displayed is set by the <xref:System.Windows.Forms.RichTextBox.Text%2A> property.</span></span> <span data-ttu-id="e5404-109">O <xref:System.Windows.Forms.RichTextBox> controle possui várias propriedades para formatar o texto.</span><span class="sxs-lookup"><span data-stu-id="e5404-109">The <xref:System.Windows.Forms.RichTextBox> control has numerous properties to format text.</span></span> <span data-ttu-id="e5404-110">Para obter detalhes sobre essas propriedades, consulte [Como definir atributos de fonte para o controle RichTextBox do Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) e [Como definir recuos, recuos deslocados e parágrafos com marcadores com o controle RichTextBox do Windows Forms](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md).</span><span class="sxs-lookup"><span data-stu-id="e5404-110">For details on these properties, see [How to: Set Font Attributes for the Windows Forms RichTextBox Control](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) and [How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md).</span></span> <span data-ttu-id="e5404-111">Para manipular arquivos, o <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> e <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> podem exibir e gravar vários formatos de arquivo, incluindo texto sem formatação, de texto sem formatação Unicode e Rich Text Format (RTF).</span><span class="sxs-lookup"><span data-stu-id="e5404-111">To manipulate files, the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> and <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> methods can display and write multiple file formats including plain text, Unicode plain text, and Rich Text Format (RTF).</span></span> <span data-ttu-id="e5404-112">Os formatos de arquivo possíveis estão listados em <xref:System.Windows.Forms.RichTextBoxStreamType>.</span><span class="sxs-lookup"><span data-stu-id="e5404-112">The possible file formats are listed in <xref:System.Windows.Forms.RichTextBoxStreamType>.</span></span> <span data-ttu-id="e5404-113">Você pode usar o <xref:System.Windows.Forms.RichTextBox.Find%2A> método de localização de cadeias de caracteres de texto ou caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="e5404-113">You can use the <xref:System.Windows.Forms.RichTextBox.Find%2A> method to find strings of text or specific characters.</span></span>  
  
 <span data-ttu-id="e5404-114">Você também pode usar um <xref:System.Windows.Forms.RichTextBox> controle de links da Web estilo definindo o <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> propriedade `true` e escrever código para manipular o <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="e5404-114">You can also use a <xref:System.Windows.Forms.RichTextBox> control for Web-style links by setting the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property to `true` and writing code to handle the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event.</span></span> <span data-ttu-id="e5404-115">Para obter mais informações, consulte [Como exibir links em estilo da Web com o controle RichTextBox do Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md).</span><span class="sxs-lookup"><span data-stu-id="e5404-115">For more information, see [How to: Display Web-Style Links with the Windows Forms RichTextBox Control](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md).</span></span> <span data-ttu-id="e5404-116">Você pode impedir que o usuário manipular parte ou todo o texto no controle definindo o <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> propriedade `true`.</span><span class="sxs-lookup"><span data-stu-id="e5404-116">You can prevent the user from manipulating some or all of the text in the control by setting the <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="e5404-117">Você pode desfazer e refazer a maioria das operações de edição em um <xref:System.Windows.Forms.RichTextBox> controle chamando o <xref:System.Windows.Forms.TextBoxBase.Undo%2A> e <xref:System.Windows.Forms.RichTextBox.Redo%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="e5404-117">You can undo and redo most edit operations in a <xref:System.Windows.Forms.RichTextBox> control by calling the <xref:System.Windows.Forms.TextBoxBase.Undo%2A> and <xref:System.Windows.Forms.RichTextBox.Redo%2A> methods.</span></span> <span data-ttu-id="e5404-118">O <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> método permite que você determine se a última operação desfez o usuário pode ser reaplicada ao controle.</span><span class="sxs-lookup"><span data-stu-id="e5404-118">The <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> method enables you to determine whether the last operation the user has undone can be reapplied to the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5404-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e5404-119">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="e5404-120">Controle RichTextBox</span><span class="sxs-lookup"><span data-stu-id="e5404-120">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="e5404-121">Visão geral do controle TextBox</span><span class="sxs-lookup"><span data-stu-id="e5404-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)