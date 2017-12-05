---
title: "Como criar uma associação duplex federada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0a44aab556e362ad82fb4d9152edd5691f4bdbd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="7bc6b-102">Como criar uma associação duplex federada</span><span class="sxs-lookup"><span data-stu-id="7bc6b-102">How to: Create a Duplex Federated Binding</span></span>
<span data-ttu-id="7bc6b-103"><xref:System.ServiceModel.WSFederationHttpBinding>suporta apenas os contratos de troca de mensagem de datagrama e solicitação/resposta.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="7bc6b-104">Para usar o contrato de troca de mensagens duplex, você deve criar uma associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="7bc6b-105">Os procedimentos a seguir mostram como fazer isso na configuração, usando segurança de modo de mensagem para os transportes HTTP e TCP e segurança de modo misto para o transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="7bc6b-106">Código de exemplo mostrando todas as associações de 3 é no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="7bc6b-107">Você também pode criar a associação no código.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-107">You can also create the binding in code.</span></span> <span data-ttu-id="7bc6b-108">Para obter uma descrição da pilha de elementos de associação para criar, consulte [como: criar uma associação personalizada utilizando o SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="7bc6b-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="7bc6b-109">Para criar uma associação personalizada duplex federada com HTTP</span><span class="sxs-lookup"><span data-stu-id="7bc6b-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1.  <span data-ttu-id="7bc6b-110">No [ \<associações >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) criar nó do arquivo de configuração, uma [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2.  <span data-ttu-id="7bc6b-111">Dentro de [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, criar um [ \<associação >](../../../../docs/framework/misc/binding.md) elemento com o `name` atributo definido como `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="7bc6b-112">Dentro de [ \<associação >](../../../../docs/framework/misc/binding.md) elemento, criar um [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento com o `authenticationMode` atributo definido como `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="7bc6b-113">Dentro de [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crie um [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento com o `authenticationMode` atributo definido como `IssuedTokenForCertificate` ou `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="7bc6b-114">Após o [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, criar vazio [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6.  <span data-ttu-id="7bc6b-115">Após o [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento, criar vazio [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7.  <span data-ttu-id="7bc6b-116">Após o [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento, criar vazio [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="7bc6b-117">Para criar uma associação personalizada duplex federada com o modo de segurança de mensagem TCP</span><span class="sxs-lookup"><span data-stu-id="7bc6b-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1.  <span data-ttu-id="7bc6b-118">No [ \<associações >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) criar nó do arquivo de configuração, uma [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="7bc6b-119">Dentro de [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, criar um [ \<associação >](../../../../docs/framework/misc/binding.md) elemento com o `name` atributo definido como `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="7bc6b-120">Dentro de [ \<associação >](../../../../docs/framework/misc/binding.md) elemento, criar um [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento com o `authenticationMode` atributo definido como `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="7bc6b-121">Dentro de [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crie um [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento com o `authenticationMode` atributo definido como `IssuedTokenForCertificate` ou `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="7bc6b-122">Após o [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, criar vazio [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="7bc6b-123">Para criar um duplex federada associação personalizada com o modo de segurança mistas de TCP</span><span class="sxs-lookup"><span data-stu-id="7bc6b-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1.  <span data-ttu-id="7bc6b-124">No [ \<associações >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) criar nó do arquivo de configuração, uma [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="7bc6b-125">Dentro de [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, criar um [ \<associação >](../../../../docs/framework/misc/binding.md) elemento com o `name` atributo definido como `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3.  <span data-ttu-id="7bc6b-126">Dentro de [ \<associação >](../../../../docs/framework/misc/binding.md) elemento, criar um [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento com o `authenticationMode` atributo definido como `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="7bc6b-127">Dentro de [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crie um [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento com o `authenticationMode` atributo definido como `IssuedTokenForCertificate` ou `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="7bc6b-128">Após o [ \<segurança >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, criar vazio [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6.  <span data-ttu-id="7bc6b-129">Após o [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, criar vazio [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="7bc6b-130">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="7bc6b-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="7bc6b-131">Exemplo com 3 associações</span><span class="sxs-lookup"><span data-stu-id="7bc6b-131">Sample with 3 Bindings</span></span>  
  
1.  <span data-ttu-id="7bc6b-132">Insira o seguinte código ao seu arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7bc6b-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bc6b-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7bc6b-133">Example</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
```