---
title: Como determinar a versão de descoberta de uma solicitação de investigação
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 356ddd76bdee0698fa446d830791f702af5742b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595117"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Como determinar a versão de descoberta de uma solicitação de investigação
Um proxy de descoberta pode expor vários pontos de extremidade de descoberta usando versões diferentes de descoberta. Quando um UDP multicast solicitação de investigação chega no proxy, que o proxy deve responder com uma mensagem de supressão multicast. Para fazer isso, ele precisaria saber a versão de descoberta da solicitação.  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Para determinar a versão de uma solicitação de investigação de descoberta  
  
1.  No método que responde a uma solicitação de investigação (por exemplo <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use estático <xref:System.ServiceModel.OperationContext.Current%2A> propriedade para pesquisar um <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> conforme mostrado no código a seguir.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a>Consulte também

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementando um proxy de descoberta](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
