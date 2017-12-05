---
title: Canal par
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e06a2efb-8e70-4299-8b0f-bfb37efb074b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f9d96f865fe83b12bc884fb16095aacddd015bf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="peer-channel"></a><span data-ttu-id="1a92b-102">Canal par</span><span class="sxs-lookup"><span data-stu-id="1a92b-102">Peer Channel</span></span>
<span data-ttu-id="1a92b-103">Este tópico lista todas as exceções geradas pelo [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] canal par.</span><span class="sxs-lookup"><span data-stu-id="1a92b-103">This topic lists all exceptions generated by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Peer Channel.</span></span>  
  
## <a name="exception-list"></a><span data-ttu-id="1a92b-104">Lista de exceções</span><span class="sxs-lookup"><span data-stu-id="1a92b-104">Exception List</span></span>  
  
|<span data-ttu-id="1a92b-105">Código do recurso</span><span class="sxs-lookup"><span data-stu-id="1a92b-105">Resource Code</span></span>|<span data-ttu-id="1a92b-106">Cadeia de caracteres de recurso</span><span class="sxs-lookup"><span data-stu-id="1a92b-106">Resource String</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="1a92b-107">InsufficientCredentials</span><span class="sxs-lookup"><span data-stu-id="1a92b-107">InsufficientCredentials</span></span>|<span data-ttu-id="1a92b-108">As credenciais especificadas não são suficientes para realizar a operação solicitada.</span><span class="sxs-lookup"><span data-stu-id="1a92b-108">The credentials specified are not sufficient to carry the requested operation.</span></span> <span data-ttu-id="1a92b-109">Especifique um valor válido para a operação especificada</span><span class="sxs-lookup"><span data-stu-id="1a92b-109">Please specify a valid value for the specified operation</span></span>|  
|<span data-ttu-id="1a92b-110">InvalidResolverMode</span><span class="sxs-lookup"><span data-stu-id="1a92b-110">InvalidResolverMode</span></span>|<span data-ttu-id="1a92b-111">O valor de PeerResolverMode especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="1a92b-111">The specified PeerResolverMode value is invalid.</span></span> <span data-ttu-id="1a92b-112">Especifique PeerResolveMode, Default ou PNRP.</span><span class="sxs-lookup"><span data-stu-id="1a92b-112">Specify either PeerResolveMode.Auto, Default, or PNRP.</span></span>|  
|<span data-ttu-id="1a92b-113">PeerNodeAborted</span><span class="sxs-lookup"><span data-stu-id="1a92b-113">PeerNodeAborted</span></span>|<span data-ttu-id="1a92b-114">PeerNode não pode ser aberto porque ele foi encerrado.</span><span class="sxs-lookup"><span data-stu-id="1a92b-114">The PeerNode cannot be opened because it has been terminated.</span></span>|  
|<span data-ttu-id="1a92b-115">PeerNullRegistrationInfo</span><span class="sxs-lookup"><span data-stu-id="1a92b-115">PeerNullRegistrationInfo</span></span>|<span data-ttu-id="1a92b-116">Informações de registro não podem ser nulas.</span><span class="sxs-lookup"><span data-stu-id="1a92b-116">Registration information cannot be null.</span></span> <span data-ttu-id="1a92b-117">Certifique-se de que a operação registrar é chamada com um objeto RegistrationInfo válido.</span><span class="sxs-lookup"><span data-stu-id="1a92b-117">Please ensure that the Register operation is invoked with a valid RegistrationInfo object.</span></span>|  
|<span data-ttu-id="1a92b-118">PeerNullResolveInfo</span><span class="sxs-lookup"><span data-stu-id="1a92b-118">PeerNullResolveInfo</span></span>|<span data-ttu-id="1a92b-119">Resolver informações não podem ser `null`.</span><span class="sxs-lookup"><span data-stu-id="1a92b-119">Resolve information cannot be `null`.</span></span> <span data-ttu-id="1a92b-120">Certifique-se de que a operação resolver é chamada com um objeto ResolveInfo válido.</span><span class="sxs-lookup"><span data-stu-id="1a92b-120">Please ensure that the Resolve operation is invoked with a valid ResolveInfo object.</span></span>|