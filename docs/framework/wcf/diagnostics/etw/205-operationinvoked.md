---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b4e101c4e9e5812c32b85029e9c24d983cb5e5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="205---operationinvoked"></a><span data-ttu-id="5646b-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="5646b-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="5646b-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="5646b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5646b-104">ID</span><span class="sxs-lookup"><span data-stu-id="5646b-104">ID</span></span>|<span data-ttu-id="5646b-105">205</span><span class="sxs-lookup"><span data-stu-id="5646b-105">205</span></span>|  
|<span data-ttu-id="5646b-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="5646b-106">Keywords</span></span>|<span data-ttu-id="5646b-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5646b-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5646b-108">Nível</span><span class="sxs-lookup"><span data-stu-id="5646b-108">Level</span></span>|<span data-ttu-id="5646b-109">Informações</span><span class="sxs-lookup"><span data-stu-id="5646b-109">Information</span></span>|  
|<span data-ttu-id="5646b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5646b-110">Channel</span></span>|<span data-ttu-id="5646b-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="5646b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5646b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="5646b-112">Description</span></span>  
 <span data-ttu-id="5646b-113">Esse evento é emitido antes de padrão do modelo de serviço `OperationInvoker` começa uma chamada para um método.</span><span class="sxs-lookup"><span data-stu-id="5646b-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5646b-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="5646b-114">Message</span></span>  
 <span data-ttu-id="5646b-115">Um OperationInvoker invocou o método '%1'.</span><span class="sxs-lookup"><span data-stu-id="5646b-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="5646b-116">Informações do chamador: '%2'.</span><span class="sxs-lookup"><span data-stu-id="5646b-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5646b-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5646b-117">Details</span></span>  
  
|<span data-ttu-id="5646b-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="5646b-118">Data Item Name</span></span>|<span data-ttu-id="5646b-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="5646b-119">Data Item Type</span></span>|<span data-ttu-id="5646b-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="5646b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5646b-121">Nome do método</span><span class="sxs-lookup"><span data-stu-id="5646b-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="5646b-122">O nome CLR do método que foi invocado pelo `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="5646b-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="5646b-123">Informações de chamador</span><span class="sxs-lookup"><span data-stu-id="5646b-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="5646b-124">O endereço IP e porta número do cliente no formato 'IPAddress:PortNumber'.</span><span class="sxs-lookup"><span data-stu-id="5646b-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="5646b-125">Os dois valores são recuperados da propriedade de mensagem 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' dentro do contexto da operação.</span><span class="sxs-lookup"><span data-stu-id="5646b-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="5646b-126">Observe que para ligações TCP não esse valor `null`.</span><span class="sxs-lookup"><span data-stu-id="5646b-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="5646b-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="5646b-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="5646b-128">Para serviços hospedados na Web, este campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="5646b-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5646b-129">O formato é definido como ' caminho Virtual do aplicativo de nome de Site da Web &#124; Caminho Virtual do serviço &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5646b-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5646b-130">Exemplo: ' Default Web Site/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5646b-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5646b-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5646b-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5646b-132">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5646b-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|