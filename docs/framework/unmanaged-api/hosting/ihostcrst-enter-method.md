---
title: "Método IHostCrst::Enter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Enter
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d209e13360616295f166ad23c65b0c4e764af79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="23079-102">Método IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="23079-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="23079-103">Entrar na seção crítica que é representada por atual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instância.</span><span class="sxs-lookup"><span data-stu-id="23079-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23079-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="23079-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23079-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="23079-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="23079-106">[in] Uma da [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indica qual ação o host deve executar se os blocos de operação.</span><span class="sxs-lookup"><span data-stu-id="23079-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23079-107">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="23079-107">Return Value</span></span>  
  
|<span data-ttu-id="23079-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23079-108">HRESULT</span></span>|<span data-ttu-id="23079-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="23079-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23079-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="23079-110">S_OK</span></span>|<span data-ttu-id="23079-111">`Enter`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="23079-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="23079-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23079-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23079-113">O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="23079-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23079-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23079-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23079-115">A chamada foi atingido.</span><span class="sxs-lookup"><span data-stu-id="23079-115">The call timed out.</span></span>|  
|<span data-ttu-id="23079-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23079-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23079-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="23079-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23079-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23079-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23079-119">Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.</span><span class="sxs-lookup"><span data-stu-id="23079-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23079-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23079-120">E_FAIL</span></span>|<span data-ttu-id="23079-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="23079-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23079-122">Quando um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo.</span><span class="sxs-lookup"><span data-stu-id="23079-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23079-123">As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="23079-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23079-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="23079-124">Remarks</span></span>  
 <span data-ttu-id="23079-125">`Enter`reflete o Win32 `EnterCriticalSection` função.</span><span class="sxs-lookup"><span data-stu-id="23079-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23079-126">Este método não retorna até que a seção crítica é inserida.</span><span class="sxs-lookup"><span data-stu-id="23079-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23079-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23079-127">Requirements</span></span>  
 <span data-ttu-id="23079-128">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23079-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23079-129">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23079-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23079-130">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="23079-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23079-131">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23079-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23079-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="23079-132">See Also</span></span>  
 [<span data-ttu-id="23079-133">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="23079-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="23079-134">Interface IHostCrst</span><span class="sxs-lookup"><span data-stu-id="23079-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="23079-135">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="23079-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)