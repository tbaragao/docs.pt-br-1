---
title: '&lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 95b2ac18f6c04ad7ba31a8b1579506ac5c3b51ab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltidentitygt"></a><span data-ttu-id="53b2e-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="53b2e-102">&lt;identity&gt;</span></span>
<span data-ttu-id="53b2e-103">O elemento de identidade permite que um desenvolvedor de cliente especificar em tempo de design a identidade esperada do serviço.</span><span class="sxs-lookup"><span data-stu-id="53b2e-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="53b2e-104">No processo de handshake entre o cliente e o serviço, o [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infraestrutura garantirá que a identidade do serviço esperado corresponde aos valores desse elemento e, portanto, pode ser autenticada.</span><span class="sxs-lookup"><span data-stu-id="53b2e-104">In the handshake process between the client and service, the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="53b2e-105">Para obter mais informações, consulte [autenticação e identidade de serviço](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="53b2e-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="53b2e-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="53b2e-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="53b2e-107">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="53b2e-107">\<client></span></span>  
<span data-ttu-id="53b2e-108">\<ponto de extremidade ></span><span class="sxs-lookup"><span data-stu-id="53b2e-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b2e-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="53b2e-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53b2e-110">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="53b2e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="53b2e-111">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="53b2e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53b2e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="53b2e-112">Attributes</span></span>  
 <span data-ttu-id="53b2e-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="53b2e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53b2e-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="53b2e-114">Child Elements</span></span>  
  
|<span data-ttu-id="53b2e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="53b2e-115">Element</span></span>|<span data-ttu-id="53b2e-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="53b2e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53b2e-117">certificado</span><span class="sxs-lookup"><span data-stu-id="53b2e-117">certificate</span></span>|<span data-ttu-id="53b2e-118">Especifica as configurações de um certificado x. 509.</span><span class="sxs-lookup"><span data-stu-id="53b2e-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="53b2e-119">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="53b2e-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="53b2e-120">Ele contém um atributo `encodedValue` que é uma cadeia de caracteres que especifica o valor codificado por esse certificado.</span><span class="sxs-lookup"><span data-stu-id="53b2e-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="53b2e-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="53b2e-121">certificateReference</span></span>|<span data-ttu-id="53b2e-122">Especifica configurações para validação do certificado x. 509.</span><span class="sxs-lookup"><span data-stu-id="53b2e-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="53b2e-123">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="53b2e-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="53b2e-124">dns</span><span class="sxs-lookup"><span data-stu-id="53b2e-124">dns</span></span>|<span data-ttu-id="53b2e-125">Especifica o DNS de um certificado x. 509 usado para autenticar um serviço.</span><span class="sxs-lookup"><span data-stu-id="53b2e-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="53b2e-126">Esse elemento contém um atributo `value` que é uma cadeia de caracteres e contém a identidade real.</span><span class="sxs-lookup"><span data-stu-id="53b2e-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="53b2e-127">rsa</span><span class="sxs-lookup"><span data-stu-id="53b2e-127">rsa</span></span>|<span data-ttu-id="53b2e-128">Especifica o valor do campo RSA de um certificado x. 509 usado para autenticar um serviço para um cliente.</span><span class="sxs-lookup"><span data-stu-id="53b2e-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="53b2e-129">Esse elemento contém um atributo `value` que é uma cadeia de caracteres e contém a identidade real</span><span class="sxs-lookup"><span data-stu-id="53b2e-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="53b2e-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="53b2e-130">servicePrincipalName</span></span>|<span data-ttu-id="53b2e-131">Especifica uma identidade de nome principal (SPN) do servidor, que é o nome de entidade de segurança usado por um cliente para identificar exclusivamente uma instância de um serviço.</span><span class="sxs-lookup"><span data-stu-id="53b2e-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="53b2e-132">Esse elemento contém um atributo `value` que é uma cadeia de caracteres e contém o nome real da entidade.</span><span class="sxs-lookup"><span data-stu-id="53b2e-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="53b2e-133">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="53b2e-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="53b2e-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="53b2e-134">userPrincipalName</span></span>|<span data-ttu-id="53b2e-135">Especifica uma identidade de nome principal (UPN) do usuário, que é o tipo de nome de logon de um usuário em uma rede.</span><span class="sxs-lookup"><span data-stu-id="53b2e-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="53b2e-136">Nome principal do usuário consiste do nome do objeto de usuário usado no Active Directory, seguido do símbolo de arroba (@) e, em seguida, em geral, o sistema de nome de domínio pai domínio.</span><span class="sxs-lookup"><span data-stu-id="53b2e-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="53b2e-137">Por exemplo, Jeff na árvore de domínio Fabrikam.com pode ter o nome principal do usuário [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Esse elemento contém um atributo `value` que é uma cadeia de caracteres e contém o nome real da entidade.</span><span class="sxs-lookup"><span data-stu-id="53b2e-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="53b2e-138">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="53b2e-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53b2e-139">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="53b2e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="53b2e-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="53b2e-140">Element</span></span>|<span data-ttu-id="53b2e-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="53b2e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53b2e-142">\<personalizado ></span><span class="sxs-lookup"><span data-stu-id="53b2e-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="53b2e-143">Especifica um resolvedor de pares personalizado para um netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="53b2e-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="53b2e-144">\<ponto de extremidade ></span><span class="sxs-lookup"><span data-stu-id="53b2e-144">\<endpoint></span></span>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="53b2e-145">Configura os diferentes tipos de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="53b2e-145">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="53b2e-146">\<emissor ></span><span class="sxs-lookup"><span data-stu-id="53b2e-146">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="53b2e-147">Especifica o serviço de Token de segurança (STS) para o serviço federado.</span><span class="sxs-lookup"><span data-stu-id="53b2e-147">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="53b2e-148">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="53b2e-148">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="53b2e-149">Especifica o ponto de extremidade de metadados para o Token de segurança Service (STS) de um serviço federado.</span><span class="sxs-lookup"><span data-stu-id="53b2e-149">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="53b2e-150">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="53b2e-150">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="53b2e-151">Define os parâmetros de um token emitido em uma associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="53b2e-151">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="53b2e-152">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="53b2e-152">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="53b2e-153">Especifica um local Security Token Service (STS).</span><span class="sxs-lookup"><span data-stu-id="53b2e-153">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53b2e-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53b2e-154">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="53b2e-155">Autenticação e identidade de serviço</span><span class="sxs-lookup"><span data-stu-id="53b2e-155">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="53b2e-156">Pontos de extremidade: Endereços, associações e contratos</span><span class="sxs-lookup"><span data-stu-id="53b2e-156">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)