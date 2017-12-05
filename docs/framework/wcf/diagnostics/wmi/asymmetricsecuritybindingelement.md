---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 104810fc24cfe7c4c6ddf7ee5ece9f16a345c80c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="41164-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="41164-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="41164-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="41164-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41164-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="41164-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="41164-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="41164-105">Methods</span></span>  
 <span data-ttu-id="41164-106">A classe AsymmetricSecurityBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="41164-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="41164-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="41164-107">Properties</span></span>  
 <span data-ttu-id="41164-108">A classe AsymmetricSecurityBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="41164-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="41164-109">messageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="41164-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="41164-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="41164-110">Data type: string</span></span>  
  
 <span data-ttu-id="41164-111">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="41164-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41164-112">A ordem de criptografia de mensagem e assinatura para essa associação.</span><span class="sxs-lookup"><span data-stu-id="41164-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="41164-113">requireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="41164-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="41164-114">Tipo de dados: boolean</span><span class="sxs-lookup"><span data-stu-id="41164-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="41164-115">Tipo de acesso: somente leitura</span><span class="sxs-lookup"><span data-stu-id="41164-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41164-116">Se a associação requer confirmação de assinatura.</span><span class="sxs-lookup"><span data-stu-id="41164-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41164-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41164-117">Requirements</span></span>  
  
|<span data-ttu-id="41164-118">MOF</span><span class="sxs-lookup"><span data-stu-id="41164-118">MOF</span></span>|<span data-ttu-id="41164-119">Declarado em Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="41164-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="41164-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="41164-120">Namespace</span></span>|<span data-ttu-id="41164-121">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="41164-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41164-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="41164-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>