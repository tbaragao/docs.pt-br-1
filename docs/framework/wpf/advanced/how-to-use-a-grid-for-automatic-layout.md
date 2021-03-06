---
title: 'Como: Usar uma grade para layout automático'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 0eda70a7d8cc5abb70b5043cbaa1d4fc418bb1f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611417"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Como: Usar uma grade para layout automático
Este exemplo descreve como usar uma grade na abordagem de layout automático para criar um aplicativo localizável.  
  
 Localização de um [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] pode ser um processo demorado. Geralmente, localizadores precisam redimensionar e reposicionar elementos além de traduzir o texto. No passado cada idioma que um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] foi adaptado exigia um ajuste. Agora, com os recursos do [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] você pode criar elementos que reduzem a necessidade de ajuste. A abordagem para escrever aplicativos que podem ser mais facilmente redimensionados e reposicionados é chamada `auto layout`.  
  
 O seguinte [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] exemplo demonstra como usar uma grade para posicionar alguns botões e texto. Observe que a altura e largura das células são definidas como `Auto`; portanto, a célula que contém o botão com uma imagem é ajustada para se adaptar à imagem. Porque o <xref:System.Windows.Controls.Grid> elemento pode ajustar a seu conteúdo pode ser útil quando adotando a abordagem de layout automático para projetar aplicativos que podem ser localizados.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como usar uma grade.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 O gráfico a seguir mostra a saída do exemplo de código.  
  
 ![Exemplo de grade](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grade  
  
## <a name="see-also"></a>Consulte também
- [Visão geral do uso de layout automático](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)
- [Usar layout automático para criar um botão](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
