---
title: "Como exportar declarações de política personalizadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1cfce32a7e7099a601c76874c8ca951488335fc6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-export-custom-policy-assertions"></a><span data-ttu-id="7f93e-102">Como exportar declarações de política personalizadas</span><span class="sxs-lookup"><span data-stu-id="7f93e-102">How to: Export Custom Policy Assertions</span></span>
<span data-ttu-id="7f93e-103">Declarações de política descrevem os recursos e requisitos de um ponto de extremidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="7f93e-103">Policy assertions describe the capabilities and requirements of a service endpoint.</span></span> <span data-ttu-id="7f93e-104">Aplicativos de serviço podem usar declarações de política personalizada nos metadados de serviço para comunicar-se o ponto de extremidade, informações de personalização de associação ou o contrato para o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="7f93e-104">Service applications can use custom policy assertions in service metadata to communicate endpoint, binding or contract customization information to the client application.</span></span> <span data-ttu-id="7f93e-105">Você pode usar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para exportar declarações em expressões de política anexadas em associações de WSDL no ponto de extremidade, operação ou entidades de mensagem, dependendo do modo como os recursos ou os requisitos que você está se comunicando.</span><span class="sxs-lookup"><span data-stu-id="7f93e-105">You can use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to export assertions in policy expressions attached in WSDL bindings at the endpoint, operation, or message subjects, depending upon the capabilities or requirements you are communicating.</span></span>  
  
 <span data-ttu-id="7f93e-106">Declarações de política personalizadas são exportadas Implementando o <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface em um <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> e inserindo o elemento de associação diretamente para a associação do ponto de extremidade de serviço ou registrando o elemento de associação em seu aplicativo arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7f93e-106">Custom policy assertions are exported by implementing the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface on a <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> and either inserting the binding element directly into the binding of the service endpoint or by registering the binding element in your application configuration file.</span></span> <span data-ttu-id="7f93e-107">A implementação de exportação de política deve adicionar a declaração de política personalizada como um <xref:System.Xml.XmlElement?displayProperty=nameWithType> instância apropriada <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType> no <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> passado para o <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> método.</span><span class="sxs-lookup"><span data-stu-id="7f93e-107">Your policy export implementation should add your custom policy assertion as a <xref:System.Xml.XmlElement?displayProperty=nameWithType> instance to the appropriate <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType> on the <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> passed into the <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> method.</span></span>  
  
 <span data-ttu-id="7f93e-108">Além disso, você deve verificar o <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> propriedade o <xref:System.ServiceModel.Description.WsdlExporter> classe e exportar expressões de política aninhados e atributos de estrutura de política no namespace correto com base na versão de política especificada.</span><span class="sxs-lookup"><span data-stu-id="7f93e-108">In addition you must check the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property of the <xref:System.ServiceModel.Description.WsdlExporter> class and export nested policy expressions and policy framework attributes in the correct namespace based on the policy version specified.</span></span>  
  
 <span data-ttu-id="7f93e-109">Para importar asserções de políticas personalizadas, consulte <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> e [como: importar declarações de política personalizada](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md).</span><span class="sxs-lookup"><span data-stu-id="7f93e-109">To import custom policy assertions, see <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> and [How to: Import Custom Policy Assertions](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md).</span></span>  
  
### <a name="to-export-custom-policy-assertions"></a><span data-ttu-id="7f93e-110">Para exportar declarações de política personalizada</span><span class="sxs-lookup"><span data-stu-id="7f93e-110">To export custom policy assertions</span></span>  
  
1.  <span data-ttu-id="7f93e-111">Implementar o <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface em um <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7f93e-111">Implement the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface on a <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7f93e-112">O exemplo de código a seguir mostra a implementação de uma declaração de política personalizada no nível de associação.</span><span class="sxs-lookup"><span data-stu-id="7f93e-112">The following code example shows the implementation of a custom policy assertion at the binding level.</span></span>  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2.  <span data-ttu-id="7f93e-113">Inserir o elemento de associação para o ponto de extremidade de associação seja programaticamente ou usando um arquivo de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7f93e-113">Insert the binding element into the endpoint binding either programmatically or using an application configuration file.</span></span> <span data-ttu-id="7f93e-114">Consulte os procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="7f93e-114">See the following procedures.</span></span>  
  
### <a name="to-insert-a-binding-element-using-an-application-configuration-file"></a><span data-ttu-id="7f93e-115">Para inserir um elemento de associação usando um arquivo de configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="7f93e-115">To insert a binding element using an application configuration file</span></span>  
  
1.  <span data-ttu-id="7f93e-116">Implementar <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> para o elemento de associação de declaração de política personalizada.</span><span class="sxs-lookup"><span data-stu-id="7f93e-116">Implement <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> for your custom policy assertion binding element.</span></span>  
  
2.  <span data-ttu-id="7f93e-117">Adicionar a extensão de elemento de associação para o arquivo de configuração usando o [ \<bindingElementExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7f93e-117">Add the binding element extension to the configuration file using the [\<bindingElementExtensions>](../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md) element.</span></span>  
  
3.  <span data-ttu-id="7f93e-118">Criar uma associação personalizada usando o <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7f93e-118">Build a custom binding using the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-insert-a-binding-element-programmatically"></a><span data-ttu-id="7f93e-119">Para inserir um elemento de associação programaticamente</span><span class="sxs-lookup"><span data-stu-id="7f93e-119">To insert a binding element programmatically</span></span>  
  
1.  <span data-ttu-id="7f93e-120">Criar um novo <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> e adicioná-lo para um <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7f93e-120">Create a new <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> and add it to a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span></span>  
  
2.  <span data-ttu-id="7f93e-121">Adicione a associação personalizada da etapa 1.</span><span class="sxs-lookup"><span data-stu-id="7f93e-121">Add the custom binding from step 1.</span></span> <span data-ttu-id="7f93e-122">para um novo ponto de extremidade e adicionar esse novo ponto de extremidade de serviço para o <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> chamando o <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="7f93e-122">to a new endpoint and add that new service endpoint to the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> by calling the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
3.  <span data-ttu-id="7f93e-123">Abra o <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7f93e-123">Open the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7f93e-124">O exemplo de código a seguir mostra a criação de uma associação personalizada e a inserção de programação de elementos de associação.</span><span class="sxs-lookup"><span data-stu-id="7f93e-124">The following code example shows the creation of a custom binding and the programmatic insertion of binding elements.</span></span>  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7f93e-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7f93e-125">See Also</span></span>  
 <xref:System.ServiceModel.Description.IPolicyImportExtension>  
 <xref:System.ServiceModel.Description.IPolicyExportExtension>  
 [<span data-ttu-id="7f93e-126">Como: importar asserções de políticas personalizadas</span><span class="sxs-lookup"><span data-stu-id="7f93e-126">How to: Import Custom Policy Assertions</span></span>](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)