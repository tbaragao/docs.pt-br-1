---
title: 'Como: Usar layout automático para criar um botão'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 501341f0e71e6e5a224c51e4ae01c68ce6b845cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543481"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Como: Usar layout automático para criar um botão
Este exemplo descreve como usar a abordagem de layout automático para criar um botão em um aplicativo localizável.  
  
 Localização de um [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] pode ser um processo demorado. Geralmente, localizadores precisam redimensionar e reposicionar elementos além de traduzir o texto. No passado cada idioma que um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] foi adaptado exigia um ajuste. Agora, com os recursos do [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] você pode criar elementos que reduzem a necessidade de ajuste. A abordagem para escrever aplicativos que podem ser mais facilmente redimensionados e reposicionados é chamada `automatic layout`.  
  
 Os dois seguintes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] exemplos criam aplicativos que criar uma instância de um botão, uma com texto em inglês e outra com texto em espanhol. Observe que o código é o mesmo, exceto para o texto; o botão é ajustada para se ajustar ao texto.  
  
## <a name="example"></a>Exemplo  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 O gráfico a seguir mostra a saída dos exemplos de código.  
  
 ![O mesmo botão com texto em diferentes idiomas](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Botão redimensionável automaticamente  
  
## <a name="see-also"></a>Consulte também
- [Visão geral do uso de layout automático](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)
- [Usar uma grade para layout automático](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
