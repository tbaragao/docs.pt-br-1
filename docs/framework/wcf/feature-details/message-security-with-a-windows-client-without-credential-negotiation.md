---
title: "Segurança de mensagem com um cliente Windows sem negociação de credencial"
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
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 943e3f32334bbf5746d3730f34371793bbd2754c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="e10ae-102">Segurança de mensagem com um cliente Windows sem negociação de credencial</span><span class="sxs-lookup"><span data-stu-id="e10ae-102">Message Security with a Windows Client without Credential Negotiation</span></span>
<span data-ttu-id="e10ae-103">O cenário a seguir mostra um [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] cliente e serviço protegido pelo protocolo Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e10ae-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service secured by the Kerberos protocol.</span></span>  
  
 <span data-ttu-id="e10ae-104">O serviço e o cliente estão no mesmo domínio ou em domínios confiáveis.</span><span class="sxs-lookup"><span data-stu-id="e10ae-104">Both the service and the client are in the same domain or trusted domains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e10ae-105">A diferença entre esse cenário e [segurança de mensagem com um cliente do Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) é que este cenário não negocia a credencial de serviço com o serviço antes de enviar a mensagem de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e10ae-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="e10ae-106">Além disso, porque isso requer o protocolo Kerberos, esse cenário requer um ambiente de domínio do Windows.</span><span class="sxs-lookup"><span data-stu-id="e10ae-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>  
  
 <span data-ttu-id="e10ae-107">![Segurança sem negociação de credencial de mensagem](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="e10ae-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>  
  
|<span data-ttu-id="e10ae-108">Característica</span><span class="sxs-lookup"><span data-stu-id="e10ae-108">Characteristic</span></span>|<span data-ttu-id="e10ae-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e10ae-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e10ae-110">Modo de segurança</span><span class="sxs-lookup"><span data-stu-id="e10ae-110">Security Mode</span></span>|<span data-ttu-id="e10ae-111">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e10ae-111">Message</span></span>|  
|<span data-ttu-id="e10ae-112">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="e10ae-112">Interoperability</span></span>|<span data-ttu-id="e10ae-113">Sim, WS-Security com clientes compatíveis do perfil de token Kerberos</span><span class="sxs-lookup"><span data-stu-id="e10ae-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|  
|<span data-ttu-id="e10ae-114">Autenticação (servidor)</span><span class="sxs-lookup"><span data-stu-id="e10ae-114">Authentication (Server)</span></span>|<span data-ttu-id="e10ae-115">Autenticação mútua do servidor e cliente</span><span class="sxs-lookup"><span data-stu-id="e10ae-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="e10ae-116">Autenticação (cliente)</span><span class="sxs-lookup"><span data-stu-id="e10ae-116">Authentication (Client)</span></span>|<span data-ttu-id="e10ae-117">Autenticação mútua do servidor e cliente</span><span class="sxs-lookup"><span data-stu-id="e10ae-117">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="e10ae-118">Integridade</span><span class="sxs-lookup"><span data-stu-id="e10ae-118">Integrity</span></span>|<span data-ttu-id="e10ae-119">Sim</span><span class="sxs-lookup"><span data-stu-id="e10ae-119">Yes</span></span>|  
|<span data-ttu-id="e10ae-120">Confidencialidade</span><span class="sxs-lookup"><span data-stu-id="e10ae-120">Confidentiality</span></span>|<span data-ttu-id="e10ae-121">Sim</span><span class="sxs-lookup"><span data-stu-id="e10ae-121">Yes</span></span>|  
|<span data-ttu-id="e10ae-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="e10ae-122">Transport</span></span>|<span data-ttu-id="e10ae-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="e10ae-123">HTTP</span></span>|  
|<span data-ttu-id="e10ae-124">Associação</span><span class="sxs-lookup"><span data-stu-id="e10ae-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="e10ae-125">Serviço</span><span class="sxs-lookup"><span data-stu-id="e10ae-125">Service</span></span>  
 <span data-ttu-id="e10ae-126">O código e a configuração a seguir destinam-se para executar de forma independente.</span><span class="sxs-lookup"><span data-stu-id="e10ae-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e10ae-127">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e10ae-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="e10ae-128">Crie um serviço autônomo usando o código sem nenhuma configuração.</span><span class="sxs-lookup"><span data-stu-id="e10ae-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="e10ae-129">Criar um serviço usando a configuração fornecida, mas não pode definir pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e10ae-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e10ae-130">Código</span><span class="sxs-lookup"><span data-stu-id="e10ae-130">Code</span></span>  
 <span data-ttu-id="e10ae-131">O código a seguir cria um ponto de extremidade de serviço que usa segurança de mensagem.</span><span class="sxs-lookup"><span data-stu-id="e10ae-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="e10ae-132">O código desativa a negociação de credencial de serviço e o estabelecimento de um token de contexto de segurança (SCT).</span><span class="sxs-lookup"><span data-stu-id="e10ae-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e10ae-133">Para usar o tipo de credencial do Windows sem negociação, a conta de usuário do serviço deve ter acesso ao nome principal do serviço (SPN) que está registrado com o domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e10ae-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="e10ae-134">Você pode fazer isso de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="e10ae-134">You can do this in two ways:</span></span>  
  
1.  <span data-ttu-id="e10ae-135">Use o `NetworkService` ou `LocalSystem` conta para executar o serviço.</span><span class="sxs-lookup"><span data-stu-id="e10ae-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="e10ae-136">Como essas contas têm acesso à máquina SPN é estabelecida quando o computador ingressa no domínio do Active Directory, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gera automaticamente o elemento SPN apropriado dentro do ponto de extremidade do serviço nos metadados do serviço (serviços Web Linguagem de descrição, ou WSDL).</span><span class="sxs-lookup"><span data-stu-id="e10ae-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>  
  
2.  <span data-ttu-id="e10ae-137">Use uma conta de domínio do Active Directory arbitrária para executar o serviço.</span><span class="sxs-lookup"><span data-stu-id="e10ae-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="e10ae-138">Nesse caso, você precisa estabelecer um SPN para essa conta de domínio.</span><span class="sxs-lookup"><span data-stu-id="e10ae-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="e10ae-139">Uma maneira de fazer isso é usar a ferramenta Setspn.exe.</span><span class="sxs-lookup"><span data-stu-id="e10ae-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="e10ae-140">Depois de criar o SPN para a conta de serviço, configurar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para publicar esse SPN para clientes do serviço por meio de seus metadados (WSDL).</span><span class="sxs-lookup"><span data-stu-id="e10ae-140">Once the SPN is created for the service's account, configure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="e10ae-141">Isso é feito definindo-se a identidade do ponto de extremidade para o ponto de extremidade exposto, em que um arquivo de configuração do aplicativo ou código.</span><span class="sxs-lookup"><span data-stu-id="e10ae-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="e10ae-142">O exemplo a seguir publica a identidade por meio de programação.</span><span class="sxs-lookup"><span data-stu-id="e10ae-142">The following example publishes the identity programmatically.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e10ae-143">Os SPNs, o protocolo Kerberos e o Active Directory, consulte [Kerberos suplemento técnico para Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="e10ae-143"> SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e10ae-144">identidades de ponto de extremidade, consulte [modos de autenticação SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="e10ae-144"> endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
 [!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]  
  
### <a name="configuration"></a><span data-ttu-id="e10ae-145">Configuração</span><span class="sxs-lookup"><span data-stu-id="e10ae-145">Configuration</span></span>  
 <span data-ttu-id="e10ae-146">A configuração a seguir pode ser usada em vez do código.</span><span class="sxs-lookup"><span data-stu-id="e10ae-146">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="KerberosBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator"   
                  listenUri="net.tcp://localhost/metadata" >  
         <identity>  
            <servicePrincipalName value="service_spn_name" />  
         </identity>  
        </endpoint>  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="KerberosBinding">  
          <security>  
            <message negotiateServiceCredential="false"   
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="e10ae-147">Cliente</span><span class="sxs-lookup"><span data-stu-id="e10ae-147">Client</span></span>  
 <span data-ttu-id="e10ae-148">O código e a configuração a seguir destinam-se para executar de forma independente.</span><span class="sxs-lookup"><span data-stu-id="e10ae-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e10ae-149">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e10ae-149">Do one of the following:</span></span>  
  
-   <span data-ttu-id="e10ae-150">Crie um cliente autônomo usando o código (e o código do cliente).</span><span class="sxs-lookup"><span data-stu-id="e10ae-150">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="e10ae-151">Crie um cliente que não define os endereços de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e10ae-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="e10ae-152">Em vez disso, use o construtor de cliente que usa o nome da configuração como um argumento.</span><span class="sxs-lookup"><span data-stu-id="e10ae-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="e10ae-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e10ae-153">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="e10ae-154">Código</span><span class="sxs-lookup"><span data-stu-id="e10ae-154">Code</span></span>  
 <span data-ttu-id="e10ae-155">O código a seguir configura o cliente.</span><span class="sxs-lookup"><span data-stu-id="e10ae-155">The following code configures the client.</span></span> <span data-ttu-id="e10ae-156">O modo de segurança é definido como mensagem e o tipo de credencial de cliente é definido como Windows.</span><span class="sxs-lookup"><span data-stu-id="e10ae-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="e10ae-157">Observe que o <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> e <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> propriedades são definidas como `false`.</span><span class="sxs-lookup"><span data-stu-id="e10ae-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e10ae-158">Para usar o tipo de credencial do Windows sem negociação, o cliente deve ser configurado com SPN da conta do serviço antes de iniciar a comunicação com o serviço.</span><span class="sxs-lookup"><span data-stu-id="e10ae-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="e10ae-159">O cliente usa o SPN para obter o token Kerberos para autenticar e proteger a comunicação com o serviço.</span><span class="sxs-lookup"><span data-stu-id="e10ae-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="e10ae-160">O exemplo a seguir mostra como configurar o cliente com o SPN do serviço.</span><span class="sxs-lookup"><span data-stu-id="e10ae-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="e10ae-161">Se você estiver usando o [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para gerar o cliente, SPN do serviço será automaticamente propagada para o cliente de metadados do serviço (WSDL), se contém os metadados do serviço Essas informações.</span><span class="sxs-lookup"><span data-stu-id="e10ae-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e10ae-162">como configurar o serviço para incluir seu SPN nos metadados do serviço, consulte a seção "Serviço" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e10ae-162"> how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>  
>   
>  <span data-ttu-id="e10ae-163">Para obter mais informações sobre SPNs, Kerberos e do Active Directory, consulte [Kerberos suplemento técnico para Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="e10ae-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e10ae-164">identidades de ponto de extremidade, consulte [modos de autenticação SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) tópico.</span><span class="sxs-lookup"><span data-stu-id="e10ae-164"> endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
 [!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]  
  
### <a name="configuration"></a><span data-ttu-id="e10ae-165">Configuração</span><span class="sxs-lookup"><span data-stu-id="e10ae-165">Configuration</span></span>  
 <span data-ttu-id="e10ae-166">O código a seguir configura o cliente.</span><span class="sxs-lookup"><span data-stu-id="e10ae-166">The following code configures the client.</span></span> <span data-ttu-id="e10ae-167">Observe que o [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) elemento deve ser definido para corresponder o SPN do serviço como registrado para a conta de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e10ae-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Windows"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <servicePrincipalName value="service_spn_name" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e10ae-168">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e10ae-168">See Also</span></span>  
 [<span data-ttu-id="e10ae-169">Visão geral de segurança</span><span class="sxs-lookup"><span data-stu-id="e10ae-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="e10ae-170">Autenticação e identidade de serviço</span><span class="sxs-lookup"><span data-stu-id="e10ae-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="e10ae-171">Modelo de segurança para o Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="e10ae-171">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)