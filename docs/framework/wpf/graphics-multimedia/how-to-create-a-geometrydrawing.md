---
title: 'Como: Criar um GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: c3312802b4a623afc10b620dbe2159d2c52a41a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646221"
---
# <a name="how-to-create-a-geometrydrawing"></a>Como: Criar um GeometryDrawing
Este exemplo mostra como criar e exibir um <xref:System.Windows.Media.GeometryDrawing>. Um <xref:System.Windows.Media.GeometryDrawing> permite que você criar uma forma com um preenchimento e uma estrutura de tópicos associando uma <xref:System.Windows.Media.Pen> e uma <xref:System.Windows.Media.Brush> com um <xref:System.Windows.Media.Geometry>. O <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> descreve a estrutura da forma, o <xref:System.Windows.Media.GeometryDrawing.Brush%2A> descreve o preenchimento da forma e o <xref:System.Windows.Media.GeometryDrawing.Pen%2A> descreve o contorno da forma.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa um <xref:System.Windows.Media.GeometryDrawing> para renderizar uma forma. A forma é descrita por um <xref:System.Windows.Media.GeometryGroup> e duas <xref:System.Windows.Media.EllipseGeometry> objetos. O interior da forma é pintado com um <xref:System.Windows.Media.LinearGradientBrush> e seu contorno é desenhado com uma <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. O <xref:System.Windows.Media.GeometryDrawing> é exibido usando um <xref:System.Windows.Media.ImageDrawing> e um <xref:System.Windows.Controls.Image> elemento.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 A ilustração a seguir mostra a resultante <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Um GeometryDrawing de duas elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Para criar desenhos mais complexos, você pode combinar vários objetos de desenho em um único desenho composto usando um <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Media.DrawingGroup>
- [Visão geral dos objetos de desenho](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [Visão geral de geometria](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [Criar um desenho composto](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
