---
title: "Como determinar a versão de descoberta de uma solicitação de investigação"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 383d96e661ca7872108b40f69be86ef4e1ca63b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="9bf3f-102">Como determinar a versão de descoberta de uma solicitação de investigação</span><span class="sxs-lookup"><span data-stu-id="9bf3f-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="9bf3f-103">Um proxy de descoberta pode expor vários pontos de extremidade de descoberta usando versões diferentes de descoberta.</span><span class="sxs-lookup"><span data-stu-id="9bf3f-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="9bf3f-104">Quando um UDP multicast investigação solicitação chega no proxy que do proxy deve responder com uma mensagem de supressão multicast.</span><span class="sxs-lookup"><span data-stu-id="9bf3f-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="9bf3f-105">Para fazer isso seria necessário saber a versão de descoberta da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9bf3f-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="9bf3f-106">Para determinar a versão de uma solicitação de investigação de descoberta</span><span class="sxs-lookup"><span data-stu-id="9bf3f-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1.  <span data-ttu-id="9bf3f-107">O método que responde a uma solicitação de investigação (por exemplo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) usar estático <xref:System.ServiceModel.OperationContext.Current%2A> propriedade para pesquisar um <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="9bf3f-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9bf3f-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9bf3f-108">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [<span data-ttu-id="9bf3f-109">Implementando um Proxy de descoberta</span><span class="sxs-lookup"><span data-stu-id="9bf3f-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [<span data-ttu-id="9bf3f-110">Exemplo de Proxy de descoberta</span><span class="sxs-lookup"><span data-stu-id="9bf3f-110">Discovery Proxy Sample</span></span>](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)