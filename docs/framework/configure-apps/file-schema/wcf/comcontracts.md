---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 3e3e4bf18b204db5a4068cc3f6cbb1337d5f611d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254308"
---
# <a name="comcontracts"></a>\<comContracts>
O `comContracts` seção de configuração contém elementos que permitem que você especificar várias propriedades de um contrato de serviço de integração COM+.  
  
## <a name="specifying-namespace-and-contract"></a>Especificando o Namespace e um contrato  
 Contratos de serviço de integração COM+ são atualmente restritos ao `http://tempuri.org` namespace, e o nome do contrato é derivado da interface COM suporte. No entanto, você pode especificar alternativas usando o `comContracts` seção no arquivo de configuração.  
  
 Por exemplo, você pode usar a configuração a seguir para especificar o nome de namespace e o contrato do contrato de serviço, bem como uma opção para impor o uso em associações de sessão.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 Quando o serviço é inicializado, os namespaces especificados e os nomes de contrato são aplicados as descrições de serviço gerado.  
  
 Quando essa seção está vazia, a inicialização de serviço aplica-se um nome de namespace e contrato padrão obtido a ID de interface COM suporte.  
  
 Além disso, você pode usar o [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elemento para especificar métodos COM+ que são expostos quando a interface em um componente COM+ é exposta como um serviço Web. Você também pode usar o [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) para especificar os tipos persistentes usados na integração. Por fim, você pode usar o [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) elemento incluir definido pelo usuário tipos (UDT) que devem ser incluídas no contrato de serviço.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)
- [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)
- [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)
- [\<comContract>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)
- [Integração de aplicativos COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Como: Definir as configurações de serviço COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
