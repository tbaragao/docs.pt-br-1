---
title: Coordenadas do Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ecb47efdd69730350cf98e1c7b1e49150ad324d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="53856-102">Coordenadas do Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53856-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="53856-103">O sistema de coordenadas para um Windows Form é baseado nas coordenadas de dispositivo e a unidade básica de medida de desenho no Windows Forms é a unidade do dispositivo (normalmente, o pixel).</span><span class="sxs-lookup"><span data-stu-id="53856-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="53856-104">Pontos na tela são descritos por pares de coordenadas x e y, com as coordenadas x aumentando para a direita e coordenadas y aumentando de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="53856-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="53856-105">O local de origem, em relação à tela, variará dependendo se você está especificando as coordenadas de tela ou de cliente.</span><span class="sxs-lookup"><span data-stu-id="53856-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="53856-106">Coordenadas de tela</span><span class="sxs-lookup"><span data-stu-id="53856-106">Screen Coordinates</span></span>  
 <span data-ttu-id="53856-107">Um Aplicativo do Windows Forms especifica a posição de uma janela na tela em coordenadas de tela.</span><span class="sxs-lookup"><span data-stu-id="53856-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="53856-108">Para coordenadas de tela, a origem é o canto superior esquerdo da tela.</span><span class="sxs-lookup"><span data-stu-id="53856-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="53856-109">A posição completa de uma janela é geralmente descrita por um <xref:System.Drawing.Rectangle> estrutura que contém as coordenadas de tela de dois pontos que definem os cantos superior esquerdo e direito inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="53856-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="53856-110">Coordenadas de cliente</span><span class="sxs-lookup"><span data-stu-id="53856-110">Client Coordinates</span></span>  
 <span data-ttu-id="53856-111">Um Aplicativo do Windows Forms especifica a posição dos pontos em um formulário ou controle usando coordenadas de cliente.</span><span class="sxs-lookup"><span data-stu-id="53856-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="53856-112">A origem das coordenadas de cliente é o canto superior esquerdo da área de cliente do controle ou formulário.</span><span class="sxs-lookup"><span data-stu-id="53856-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="53856-113">Coordenadas de cliente garantem que um aplicativo pode usar valores de coordenadas consistentes ao desenhar em um formulário ou controle, independentemente da posição do formulário ou controle na tela.</span><span class="sxs-lookup"><span data-stu-id="53856-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="53856-114">As dimensões da área cliente também são descritas por um <xref:System.Drawing.Rectangle> estrutura que contém as coordenadas do cliente para a área.</span><span class="sxs-lookup"><span data-stu-id="53856-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="53856-115">Em todos os casos, a coordenada superior esquerda do retângulo está incluída na área de cliente, enquanto a coordenada inferior direita é excluída.</span><span class="sxs-lookup"><span data-stu-id="53856-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="53856-116">Operações de elementos gráficos não incluem bordas direita e inferiores de uma área de cliente.</span><span class="sxs-lookup"><span data-stu-id="53856-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="53856-117">Por exemplo o <xref:System.Drawing.Graphics.FillRectangle%2A> método preencherá até a borda direita e inferior do retângulo especificado, mas não incluirá essas bordas.</span><span class="sxs-lookup"><span data-stu-id="53856-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="53856-118">Mapeamento de um tipo de coordenada para outro</span><span class="sxs-lookup"><span data-stu-id="53856-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="53856-119">Ocasionalmente, pode ser recomendável mapear das coordenadas de tela para as coordenadas de cliente.</span><span class="sxs-lookup"><span data-stu-id="53856-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="53856-120">Você pode fazer isso facilmente usando o <xref:System.Windows.Forms.Control.PointToClient%2A> e <xref:System.Windows.Forms.Control.PointToScreen%2A> métodos disponíveis a <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="53856-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="53856-121">Por exemplo, o <xref:System.Windows.Forms.Control.MousePosition%2A> propriedade <xref:System.Windows.Forms.Control> é relatada em coordenadas da tela, mas você pode convertê-los para coordenadas do cliente.</span><span class="sxs-lookup"><span data-stu-id="53856-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53856-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53856-122">See Also</span></span>  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>