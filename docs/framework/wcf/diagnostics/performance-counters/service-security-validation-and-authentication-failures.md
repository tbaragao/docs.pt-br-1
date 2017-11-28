---
title: "Serviço: falhas de autenticação e validação de segurança"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 808c0d648043df6c5a3dda4646e45ba1492345a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="e3609-102">Serviço: falhas de autenticação e validação de segurança</span><span class="sxs-lookup"><span data-stu-id="e3609-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="e3609-103">Nome do contador: falhas de autenticação e validação de segurança</span><span class="sxs-lookup"><span data-stu-id="e3609-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="e3609-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3609-104">Description</span></span>  
 <span data-ttu-id="e3609-105">Esse contador é incrementado sempre que uma mensagem foi rejeitada devido a um problema de segurança não coberto pelo contador "Chamadas de segurança não autorizado".</span><span class="sxs-lookup"><span data-stu-id="e3609-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="e3609-106">Esses problemas incluem:</span><span class="sxs-lookup"><span data-stu-id="e3609-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="e3609-107">Não é possível ler o token de cliente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e3609-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="e3609-108">Token de cliente falha na autenticação (por exemplo, a senha incorreta).</span><span class="sxs-lookup"><span data-stu-id="e3609-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="e3609-109">Falha na verificação de assinatura (por exemplo, a mensagem foi violada).</span><span class="sxs-lookup"><span data-stu-id="e3609-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="e3609-110">A mensagem é uma duplicata da anterior, o que pode ocorrer durante um ataque de repetição.</span><span class="sxs-lookup"><span data-stu-id="e3609-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="e3609-111">Ocorreu uma falha de descriptografia.</span><span class="sxs-lookup"><span data-stu-id="e3609-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="e3609-112">Alguns necessários faltam elementos (por exemplo, timestamp ausente ou bloquear os dados criptografados) da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e3609-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="e3609-113">Ocorreram erros durante o handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="e3609-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>