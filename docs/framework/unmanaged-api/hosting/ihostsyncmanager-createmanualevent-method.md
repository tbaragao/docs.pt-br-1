---
title: "Método IHostSyncManager::CreateManualEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7b43a6b26c3788708419d3598e95bba1273dcb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="7c9bd-102">Método IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="7c9bd-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="7c9bd-103">Cria um objeto de evento de redefinição manual.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c9bd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7c9bd-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c9bd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7c9bd-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="7c9bd-106">[in] `true`, se o objeto for sinalizado; caso contrário, `false`.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="7c9bd-107">[out] Um ponteiro para o endereço de um [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instância ou nulo se o evento não pôde ser criado.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c9bd-108">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="7c9bd-108">Return Value</span></span>  
  
|<span data-ttu-id="7c9bd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c9bd-109">HRESULT</span></span>|<span data-ttu-id="7c9bd-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c9bd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c9bd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c9bd-111">S_OK</span></span>|<span data-ttu-id="7c9bd-112">`CreateManualEvent`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7c9bd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c9bd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c9bd-114">O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c9bd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c9bd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c9bd-116">A chamada foi atingido.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-116">The call timed out.</span></span>|  
|<span data-ttu-id="7c9bd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c9bd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c9bd-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c9bd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c9bd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c9bd-120">Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c9bd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c9bd-121">E_FAIL</span></span>|<span data-ttu-id="7c9bd-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c9bd-123">Quando um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c9bd-124">As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c9bd-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7c9bd-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7c9bd-126">Não havia memória suficiente disponível para criar o objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c9bd-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="7c9bd-127">Remarks</span></span>  
 <span data-ttu-id="7c9bd-128">`CreateManualEvent`cria um `IHostManualEvent`, um objeto de evento de redefinição manual que exige uma chamada para o [Ihostmanualevent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) método defini-lo para um estado não sinalizado.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="7c9bd-129">`CreateManualEvent`reflete o Win32 `CreateEvent` função com um valor de `true` especificado para o `bManualReset` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7c9bd-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c9bd-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c9bd-130">Requirements</span></span>  
 <span data-ttu-id="7c9bd-131">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c9bd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c9bd-132">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c9bd-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c9bd-133">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="7c9bd-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c9bd-134">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c9bd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c9bd-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7c9bd-135">See Also</span></span>  
 [<span data-ttu-id="7c9bd-136">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7c9bd-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="7c9bd-137">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="7c9bd-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="7c9bd-138">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7c9bd-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)