---
title: 'Como: Criar uma curva de Bézier quadrática'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: a5d424f3fda3957bf54d7073d41d9fe2dabb1736
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650087"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a>Como: Criar uma curva de Bézier quadrática
Este exemplo mostra como criar uma curva de Bezier quadrática.  Para criar uma curva de Bezier quadrática, use o <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.QuadraticBezierSegment> classes.  
  
## <a name="example"></a>Exemplo  
 Nos exemplos a seguir, uma curva de Bezier quadrática é desenhada de (10,100) (300,100). A curva tem um ponto de controle de (200, 200).  
  
 [xaml]  
  
 No [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], você pode usar a sintaxe de atributo para descrever um caminho.  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 [xaml]  
  
 (Observe que essa sintaxe de atributo na verdade cria um <xref:System.Windows.Media.StreamGeometry>, uma versão leve de um <xref:System.Windows.Media.PathGeometry>. Para obter mais informações, consulte o [sintaxe de marcação de caminho](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) página.)  
  
 No [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], você também pode desenhar uma curva de Bezier quadrática usando sintaxe de elemento de objeto. A seguir é equivalente ao anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] exemplo.  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Este exemplo faz parte de um exemplo maior; para ver o exemplo completo, confira o [Exemplo de geometrias](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Consulte também
- [Criar um arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)
- [Criar uma curva de Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
