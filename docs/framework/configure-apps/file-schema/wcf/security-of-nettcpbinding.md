---
title: "&lt;segurança&gt; de &lt;netTcpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3873c3fd04e2f52e6d2a3bdc64e82f87c84aaf5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltnettcpbindinggt"></a><span data-ttu-id="cb670-102">&lt;segurança&gt; de &lt;netTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="cb670-102">&lt;security&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="cb670-103">Define as configurações de segurança para uma associação.</span><span class="sxs-lookup"><span data-stu-id="cb670-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="cb670-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cb670-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb670-105">\<associações ></span><span class="sxs-lookup"><span data-stu-id="cb670-105">\<bindings></span></span>  
<span data-ttu-id="cb670-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="cb670-106">\<netTcpBinding></span></span>  
<span data-ttu-id="cb670-107">\<associação ></span><span class="sxs-lookup"><span data-stu-id="cb670-107">\<binding></span></span>  
<span data-ttu-id="cb670-108">\<segurança ></span><span class="sxs-lookup"><span data-stu-id="cb670-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb670-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cb670-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
           protectionLevel="None/Sign/EncryptAndSign" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb670-110">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="cb670-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cb670-111">As seções a seguir descrevem os elementos pai de atributos e elementos filho</span><span class="sxs-lookup"><span data-stu-id="cb670-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb670-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cb670-112">Attributes</span></span>  
  
|<span data-ttu-id="cb670-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="cb670-113">Attribute</span></span>|<span data-ttu-id="cb670-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb670-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb670-115">modo</span><span class="sxs-lookup"><span data-stu-id="cb670-115">mode</span></span>|<span data-ttu-id="cb670-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cb670-116">Optional.</span></span> <span data-ttu-id="cb670-117">Especifica o tipo de segurança que é aplicada.</span><span class="sxs-lookup"><span data-stu-id="cb670-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="cb670-118">Os valores válidos são mostrados abaixo.</span><span class="sxs-lookup"><span data-stu-id="cb670-118">Valid values are shown below.</span></span> <span data-ttu-id="cb670-119">O valor padrão é `Transport`.</span><span class="sxs-lookup"><span data-stu-id="cb670-119">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="cb670-120">Esse atributo é do tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cb670-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="cb670-121">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="cb670-121">mode Attribute</span></span>  
  
|<span data-ttu-id="cb670-122">Valor</span><span class="sxs-lookup"><span data-stu-id="cb670-122">Value</span></span>|<span data-ttu-id="cb670-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb670-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb670-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cb670-124">None</span></span>|<span data-ttu-id="cb670-125">A segurança é desabilitada.</span><span class="sxs-lookup"><span data-stu-id="cb670-125">Security is disabled.</span></span>|  
|<span data-ttu-id="cb670-126">Transporte</span><span class="sxs-lookup"><span data-stu-id="cb670-126">Transport</span></span>|<span data-ttu-id="cb670-127">Segurança de transporte é fornecida com o uso de TLS sobre TCP ou SPNego.</span><span class="sxs-lookup"><span data-stu-id="cb670-127">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="cb670-128">O serviço precisará ser configurado com certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="cb670-128">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="cb670-129">É possível controlar o nível de proteção com esse modo.</span><span class="sxs-lookup"><span data-stu-id="cb670-129">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="cb670-130">Mensagem</span><span class="sxs-lookup"><span data-stu-id="cb670-130">Message</span></span>|<span data-ttu-id="cb670-131">A segurança é fornecida usando a segurança de mensagem SOAP.</span><span class="sxs-lookup"><span data-stu-id="cb670-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="cb670-132">Por padrão, o corpo SOAP é criptografado e assinado.</span><span class="sxs-lookup"><span data-stu-id="cb670-132">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="cb670-133">Esse modo oferece uma variedade de recursos, como se as credenciais de serviço estão disponíveis no cliente fora da banda, o conjunto de algoritmos para usar e o nível de proteção para aplicar ao corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="cb670-133">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="cb670-134">Autenticação de cliente é executada uma vez por sessão e os resultados de autenticação são armazenados em cache para a duração da sessão.</span><span class="sxs-lookup"><span data-stu-id="cb670-134">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="cb670-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="cb670-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="cb670-136">Segurança de transporte é associada a segurança de mensagem.</span><span class="sxs-lookup"><span data-stu-id="cb670-136">Transport security is coupled with message security.</span></span> <span data-ttu-id="cb670-137">Segurança de transporte é fornecida por TLS sobre TCP ou SPNego e garante a integridade, a confidencialidade e a autenticação do servidor.</span><span class="sxs-lookup"><span data-stu-id="cb670-137">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="cb670-138">Segurança de mensagens SOAP fornece autenticação de cliente.</span><span class="sxs-lookup"><span data-stu-id="cb670-138">SOAP message security provides client authentication.</span></span> <span data-ttu-id="cb670-139">Por padrão, autenticação de cliente é executada uma vez por sessão e os resultados de autenticação são armazenados em cache para a duração da sessão.</span><span class="sxs-lookup"><span data-stu-id="cb670-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb670-140">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="cb670-140">Child Elements</span></span>  
  
|<span data-ttu-id="cb670-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb670-141">Element</span></span>|<span data-ttu-id="cb670-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb670-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb670-143">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="cb670-143">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|<span data-ttu-id="cb670-144">Define as configurações de segurança para o transporte.</span><span class="sxs-lookup"><span data-stu-id="cb670-144">Defines the security settings for the transport.</span></span> <span data-ttu-id="cb670-145">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="cb670-145">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="cb670-146">\<mensagem ></span><span class="sxs-lookup"><span data-stu-id="cb670-146">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|<span data-ttu-id="cb670-147">Define as configurações de segurança para a mensagem.</span><span class="sxs-lookup"><span data-stu-id="cb670-147">Defines the security settings for the message.</span></span> <span data-ttu-id="cb670-148">Esse elemento é do tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span><span class="sxs-lookup"><span data-stu-id="cb670-148">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb670-149">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="cb670-149">Parent Elements</span></span>  
  
|<span data-ttu-id="cb670-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb670-150">Element</span></span>|<span data-ttu-id="cb670-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb670-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb670-152">associação</span><span class="sxs-lookup"><span data-stu-id="cb670-152">binding</span></span>|<span data-ttu-id="cb670-153">O elemento de associação do [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cb670-153">The binding element of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb670-154">Comentários</span><span class="sxs-lookup"><span data-stu-id="cb670-154">Remarks</span></span>  
 <span data-ttu-id="cb670-155">Cada uma das associações padrão fornece parâmetros para controlar os requisitos de segurança de transferência.</span><span class="sxs-lookup"><span data-stu-id="cb670-155">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="cb670-156">Normalmente, esses parâmetros incluem o modo de segurança especificado se a segurança de nível de mensagem ou nível de transporte é usada e a escolha do tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="cb670-156">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="cb670-157">Com base na escolha das opções esses parâmetros presentes, uma pilha de canais é construído com a segurança apropriada.</span><span class="sxs-lookup"><span data-stu-id="cb670-157">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="cb670-158">As associações fornecidas pelo sistema fornecidas pelo Windows Communication Foundation (WCF) são um conjunto projetado para atender a alguns dos requisitos do cenário mais comuns.</span><span class="sxs-lookup"><span data-stu-id="cb670-158">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="cb670-159">Cada uma dessas vinculações permite a especificação dos requisitos de segurança para alguns cenários de destino específicos.</span><span class="sxs-lookup"><span data-stu-id="cb670-159">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="cb670-160">Este elemento de configuração fornece as especificações de segurança para `netTcpBinding`.</span><span class="sxs-lookup"><span data-stu-id="cb670-160">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="cb670-161">Isso é uma associação segura, confiável e otimizada adequada para comunicação entre computadores.</span><span class="sxs-lookup"><span data-stu-id="cb670-161">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="cb670-162">Por padrão, ele gera uma pilha de comunicação em tempo de execução com suporte a TCP para entrega de mensagens e a segurança do Windows para segurança de mensagem e autenticação, WS-ReliableMessaging de confiabilidade e a codificação de mensagem binária.</span><span class="sxs-lookup"><span data-stu-id="cb670-162">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb670-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cb670-163">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpSecurity>  
 <xref:System.ServiceModel.NetTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="cb670-164">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="cb670-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="cb670-165">[Bindings](../../../../../docs/framework/wcf/bindings.md) (Associações)</span><span class="sxs-lookup"><span data-stu-id="cb670-165">[Bindings](../../../../../docs/framework/wcf/bindings.md)</span></span>  
 [<span data-ttu-id="cb670-166">Configurando associações fornecidas pelo sistema</span><span class="sxs-lookup"><span data-stu-id="cb670-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="cb670-167">Usando associações para configurar clientes e serviços do Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="cb670-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="cb670-168">\<associação ></span><span class="sxs-lookup"><span data-stu-id="cb670-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)