---
title: Visão geral das declarações de associação
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
ms.openlocfilehash: f31a13096d8bd3a788e530b480fece448bfe1e6e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704011"
---
# <a name="binding-declarations-overview"></a>Visão geral das declarações de associação
Este tópico discute as diferentes maneiras que você pode declarar uma associação.  
  
 
  
<a name="Prereq"></a>   
## <a name="prerequisites"></a>Pré-requisitos  
 Antes de ler este tópico, é importante que você esteja familiarizado com o conceito e o uso de extensões de marcação. Para obter mais informações sobre extensões de marcação, consulte [Extensões de marcação e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Este tópico não aborda os conceitos de vinculação de dados. Para uma discussão sobre conceitos de vinculação de dados, consulte [Visão geral da vinculação de dados](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="BindinginXAML"></a>   
## <a name="declaring-a-binding-in-xaml"></a>Declarando uma associação em XAML  
 Esta seção discute como declarar uma associação em XAML.  
  
<a name="MarkupExtensionSyntax"></a>   
### <a name="markup-extension-usage"></a>Uso da extensão de marcação  
 <xref:System.Windows.Data.Binding> é uma extensão da marcação. Quando você usa a extensão de associação para declarar uma associação, a declaração consiste em uma série de cláusulas após a palavra-chave `Binding` separadas por vírgulas (,). As cláusulas na declaração da associação podem estar em qualquer ordem e há várias combinações possíveis. As cláusulas são *nome*=*valor* pares onde *nome* é o nome da <xref:System.Windows.Data.Binding> propriedade e *valor* é o valor que você está definindo a propriedade.  
  
 Ao criar cadeias de caracteres de declaração de associação em marcação, elas devem ser anexadas à propriedade de dependência específica de um objeto de destino. O exemplo a seguir mostra como associar o <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> propriedade usando a extensão de associação, especificando as <xref:System.Windows.Data.Binding.Source%2A> e <xref:System.Windows.Data.Binding.Path%2A> propriedades.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]  
  
 Você pode especificar a maioria das propriedades do <xref:System.Windows.Data.Binding> classe dessa maneira. Para obter mais informações sobre as extensões de associação, bem como uma lista de <xref:System.Windows.Data.Binding> propriedades que não podem ser definidas usando a extensão de associação, consulte o [extensão de marcação de associação](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) visão geral.  
  
<a name="ObjectElementSyntax"></a>   
### <a name="object-element-syntax"></a>Sintaxe de elemento de objeto  
 A sintaxe de elemento de objeto é uma alternativa para criar a declaração de associação. Na maioria dos casos, não há nenhuma vantagem em particular para usar a extensão de marcação ou a sintaxe de elemento de objeto. No entanto, nos casos em que a extensão de marcação não dá suporte ao seu cenário, como quando o valor da propriedade é de um tipo sem cadeia de caracteres para o qual não há conversão de tipo, você precisa usar a sintaxe de elemento de objeto.  
  
 Este é um exemplo de sintaxe de elemento de objeto e do uso da extensão de marcação:  
  
 [!code-xaml[BindConversionMarkup#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 O exemplo associa o <xref:System.Windows.Controls.TextBlock.Foreground%2A> propriedade, declarando uma associação usando a sintaxe de extensão. A declaração de associação para o <xref:System.Windows.Controls.TextBlock.Text%2A> propriedade usa a sintaxe de elemento de objeto.  
  
 Para obter mais informações sobre diferentes termos, consulte [Sintaxe de XAML em detalhes](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="MBandPB"></a>   
### <a name="multibinding-and-prioritybinding"></a>MultiBinding e PriorityBinding  
 <xref:System.Windows.Data.MultiBinding> e <xref:System.Windows.Data.PriorityBinding> não dão suporte a sintaxe de extensão do XAML. Portanto, você deve usar a sintaxe de elemento de objeto se você está declarando uma <xref:System.Windows.Data.MultiBinding> ou um <xref:System.Windows.Data.PriorityBinding> em XAML.  
  
<a name="BindinginCode"></a>   
## <a name="creating-a-binding-in-code"></a>Criar uma associação em código  
 Outra maneira de especificar uma associação é definir propriedades diretamente em um <xref:System.Windows.Data.Binding> objeto no código. O exemplo a seguir mostra como criar um <xref:System.Windows.Data.Binding> do objeto e especifique as propriedades no código.  Neste exemplo, `TheConverter` é um objeto que implementa o <xref:System.Windows.Data.IValueConverter> interface.  
  
 [!code-csharp[BindConversion#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
  
 Se o objeto que você está associando é um <xref:System.Windows.FrameworkElement> ou um <xref:System.Windows.FrameworkContentElement> você pode chamar o `SetBinding` método em seu objeto diretamente em vez de usar <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>. Para obter um exemplo, consulte [Criar uma associação em código](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md).  
  
<a name="Path_Syntax"></a>   
## <a name="binding-path-syntax"></a>Sintaxe do caminho de associação  
 Use o <xref:System.Windows.Data.Binding.Path%2A> propriedade para especificar o valor de origem que você deseja associar a:  
  
-   No caso mais simples, o <xref:System.Windows.Data.Binding.Path%2A> o valor da propriedade é o nome da propriedade do objeto fonte a ser usada para a associação, como `Path=PropertyName`.  
  
-   Subpropriedades de uma propriedade podem ser especificadas por uma sintaxe similar como em C#. Por exemplo, a cláusula `Path=ShoppingCart.Order` define a associação com a subpropriedade `Order` do objeto ou da propriedade `ShoppingCart`.  
  
-   Para associar a uma propriedade anexada, coloque parênteses na propriedade anexada. Por exemplo, para associar a propriedade anexada <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, a sintaxe é `Path=(DockPanel.Dock)`.  
  
-   Os indexadores de uma propriedade podem ser especificados dentro de colchetes após o nome da propriedade na qual o indexador é aplicado. Por exemplo, a cláusula `Path=ShoppingCart[0]` define a associação ao índice que corresponde a como a indexação interna de sua propriedade lida com a cadeia de caracteres literal "0". Os indexadores aninhados também têm suporte.  
  
-   Os indexadores e as subpropriedades podem ser combinados em uma cláusula `Path`. Por exemplo,`Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`  
  
-   Dentro dos indexadores, você pode ter vários parâmetros de indexador separados por vírgulas (,). O tipo de cada parâmetro pode ser especificado com parênteses. Por exemplo, você pode ter `Path="[(sys:Int32)42,(sys:Int32)24]"`, em que `sys` é mapeado para o namespace `System`.  
  
-   Quando a fonte é uma exibição de coleção, o item atual pode ser especificado com uma barra (/). Por exemplo, a cláusula `Path=/` define a associação ao item atual no modo de exibição. Quando a fonte é uma coleção, essa sintaxe especifica o item atual da exibição de coleção padrão.  
  
-   Barras e nomes de propriedade podem ser combinados para percorrer as propriedades que são coleções. Por exemplo, `Path=/Offices/ManagerName` especifica o item atual da coleção de origem, que contém uma propriedade `Offices` que também é uma coleção. O item atual é um objeto que contém uma propriedade `ManagerName`.  
  
-   Opcionalmente, um caminho de ponto (.) pode ser usado para associação à fonte atual. Por exemplo, `Text="{Binding}"` equivale a `Text="{Binding Path=.}"`.  
  
### <a name="escaping-mechanism"></a>Mecanismo de escape  
  
-   Dentro dos indexadores ([]), o caractere de acento circunflexo (^) pula o próximo caractere.  
  
-   Se você definir <xref:System.Windows.Data.Binding.Path%2A> em XAML, você também precisará pular (usando entidades XML) certos caracteres que são especiais para a definição de linguagem XML:  
  
    -   Use `&` para pular o caractere "&".  
  
    -   Use `>` para pular a marca de fim ">".  
  
-   Além disso, se você descreve a associação inteira em um atributo usando a sintaxe de extensão de marcação, você precisa pular (usando a barra invertida \\) caracteres que são especiais para o analisador de extensão de marcação [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
    -   A barra invertida (\\) é o caractere de escape.  
  
    -   O sinal de igual (=) separa o nome da propriedade do valor da propriedade.  
  
    -   A vírgula (,) separa as propriedades.  
  
    -   A chave direita (}) é o final de uma extensão de marcação.  
  
<a name="Default"></a>   
## <a name="default-behaviors"></a>Comportamentos padrão  
 O comportamento padrão será o seguinte se não for especificado na declaração.  
  
-   É criado um conversor padrão que tenta fazer uma conversão de tipos entre o valor de origem de associação e o valor de destino de associação. Se a conversão não puder ser realizada, o conversor padrão retornará `null`.  
  
-   Se você não definir <xref:System.Windows.Data.Binding.ConverterCulture%2A>, o mecanismo de associação usa o `Language` propriedade do objeto de destino de associação. No XAML, esse padrão é "en-US" ou herda o valor do elemento raiz (ou qualquer elemento) da página, se um tiver sido definido explicitamente.  
  
-   Contanto que a associação já tem um contexto de dados (por exemplo, o contexto de dados herdado proveniente de um elemento pai), e qualquer item ou coleção que está sendo retornada por esse contexto é adequada para associação sem a necessidade de modificação adicional de caminho, um declaração de associação não pode ter nenhum cláusulas em todos os: `{Binding}` Isso geralmente é a maneira que uma associação é especificada para estilos de dados, onde a associação age em uma coleção. Para obter mais informações, consulte a seção "Todos os objetos usados como uma origem de associação" em [Visão geral das origens da associação](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
-   O padrão <xref:System.Windows.Data.Binding.Mode%2A> varia entre unidirecional e bidirecional, dependendo da propriedade de dependência que está sendo associada. Você sempre pode declarar o modo de associação explicitamente para garantir que sua associação tenha o comportamento desejado. Nas propriedades de controle editáveis pelo usuário, geral, como <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, padrão como vinculações bidirecionais, enquanto a maioria das outras propriedades padrão para a associação unidirecional.  
  
-   O padrão <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor varia entre <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> e <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> , dependendo da propriedade de dependência associada também. O valor padrão para a maioria das propriedades de dependência é <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, enquanto a propriedade <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> tem um valor padrão de <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.  
  
## <a name="see-also"></a>Consulte também
- [Visão geral da vinculação de dados](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Tópicos de instruções](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
- [Associação de dados](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Sintaxe PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)
