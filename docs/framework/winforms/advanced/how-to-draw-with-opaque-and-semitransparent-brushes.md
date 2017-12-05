---
title: "Como desenhar com pincéis opacos e semitransparentes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4af2664851ed0903a362a4b88edf1db9bb042dfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="9ebf7-102">Como desenhar com pincéis opacos e semitransparentes</span><span class="sxs-lookup"><span data-stu-id="9ebf7-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="9ebf7-103">Quando você preencher uma forma, você deve passar um <xref:System.Drawing.Brush> objeto para um dos métodos de preenchimento a <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="9ebf7-104">Um parâmetro do <xref:System.Drawing.SolidBrush.%23ctor%2A> construtor é um <xref:System.Drawing.Color> objeto.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="9ebf7-105">Para preencher uma forma opaca, defina o componente alfa da cor como 255.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="9ebf7-106">Para preencher uma forma semitransparente, defina o componente alfa para qualquer valor de 1 a 254.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="9ebf7-107">Ao preencher uma forma semitransparente, a cor da forma é combinada com as cores da tela de fundo.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="9ebf7-108">O componente alfa especifica como as cores da tela de fundo e da forma são misturadas; valores alfa próximos a 0 colocam mais peso nas cores da tela de fundo e valores alfabéticos próximos 255 colocam mais peso na cor da forma.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ebf7-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9ebf7-109">Example</span></span>  
 <span data-ttu-id="9ebf7-110">O exemplo a seguir desenha um bitmap e, em seguida, preenche três elipses que sobrepõem o bitmap.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="9ebf7-111">A primeira elipse usa um componente alfa de 255, portanto, é opaca.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="9ebf7-112">As segunda e terceira elipses usam um componente alfa de 128, para que sejam semitransparentes; É possível ver a imagem da tela de fundo pelas elipses.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="9ebf7-113">A chamada que define o <xref:System.Drawing.Graphics.CompositingQuality%2A> propriedade faz com que a mesclagem para a terceira elipse ser feita em conjunto com correção gama.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="9ebf7-114">A seguinte ilustração mostra a saída do código a seguir.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="9ebf7-115">![Opacas e semitransparentes](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")</span><span class="sxs-lookup"><span data-stu-id="9ebf7-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ebf7-116">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="9ebf7-116">Compiling the Code</span></span>  
 <span data-ttu-id="9ebf7-117">O exemplo anterior é projetado para uso com o Windows Forms e requer <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9ebf7-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ebf7-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9ebf7-118">See Also</span></span>  
 [<span data-ttu-id="9ebf7-119">Elementos Gráficos e Desenho nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ebf7-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="9ebf7-120">Combinação Alfa em Linhas e Preenchimentos</span><span class="sxs-lookup"><span data-stu-id="9ebf7-120">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="9ebf7-121">Como dar ao controle uma tela de fundo transparente</span><span class="sxs-lookup"><span data-stu-id="9ebf7-121">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="9ebf7-122">Como Desenhar Linhas Opacas e Semitransparentes</span><span class="sxs-lookup"><span data-stu-id="9ebf7-122">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)