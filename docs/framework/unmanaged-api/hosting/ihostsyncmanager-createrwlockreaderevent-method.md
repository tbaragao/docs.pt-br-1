---
title: "Método IHostSyncManager::CreateRWLockReaderEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockReaderEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a783f4511e27b5d230a90444e5a91b34327543cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="a6092-102">Método IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="a6092-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="a6092-103">Cria um objeto de evento de redefinição manual para a implementação de um bloqueio de leitor.</span><span class="sxs-lookup"><span data-stu-id="a6092-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6092-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a6092-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6092-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a6092-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="a6092-106">[in] `true`, se `ppEvent` devem ser sinalizado; caso contrário, `false`.</span><span class="sxs-lookup"><span data-stu-id="a6092-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="a6092-107">[in] Um cookie para associar o bloqueio de leitor.</span><span class="sxs-lookup"><span data-stu-id="a6092-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="a6092-108">[out] Um ponteiro para o endereço de um [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instância ou nulo se não foi possível criar o objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="a6092-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6092-109">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="a6092-109">Return Value</span></span>  
  
|<span data-ttu-id="a6092-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6092-110">HRESULT</span></span>|<span data-ttu-id="a6092-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="a6092-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6092-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6092-112">S_OK</span></span>|<span data-ttu-id="a6092-113">`CreateRWLockReaderEvent`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="a6092-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a6092-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a6092-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a6092-115">O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a6092-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a6092-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a6092-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a6092-117">A chamada foi atingido.</span><span class="sxs-lookup"><span data-stu-id="a6092-117">The call timed out.</span></span>|  
|<span data-ttu-id="a6092-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a6092-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a6092-119">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="a6092-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a6092-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a6092-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a6092-121">Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.</span><span class="sxs-lookup"><span data-stu-id="a6092-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a6092-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a6092-122">E_FAIL</span></span>|<span data-ttu-id="a6092-123">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="a6092-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a6092-124">Quando um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo.</span><span class="sxs-lookup"><span data-stu-id="a6092-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a6092-125">As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a6092-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a6092-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a6092-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a6092-127">Não havia memória suficiente disponível para criar o objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="a6092-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6092-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="a6092-128">Remarks</span></span>  
 <span data-ttu-id="a6092-129">O CLR chama `CreateRWLockReaderEvent` para obter uma referência a um `IHostManualEvent` instância para usar em sua implementação de um bloqueio de leitor.</span><span class="sxs-lookup"><span data-stu-id="a6092-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="a6092-130">O host pode usar o cookie para determinar quais tarefas estão aguardando o bloqueio de leitor consultando o [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="a6092-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6092-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6092-131">Requirements</span></span>  
 <span data-ttu-id="a6092-132">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6092-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6092-133">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6092-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6092-134">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="a6092-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6092-135">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6092-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6092-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a6092-136">See Also</span></span>  
 [<span data-ttu-id="a6092-137">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a6092-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="a6092-138">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="a6092-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="a6092-139">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="a6092-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="a6092-140">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a6092-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)