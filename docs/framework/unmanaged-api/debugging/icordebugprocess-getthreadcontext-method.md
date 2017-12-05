---
title: "Método ICorDebugProcess::GetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9cb2b0be2954c041b364f9c85c40570a9f04421f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="147a5-102">Método ICorDebugProcess::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="147a5-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="147a5-103">Obtém o contexto do thread especificado neste processo.</span><span class="sxs-lookup"><span data-stu-id="147a5-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="147a5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="147a5-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="147a5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="147a5-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="147a5-106">[in] A ID do thread para o qual recuperar o contexto.</span><span class="sxs-lookup"><span data-stu-id="147a5-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="147a5-107">[in] O tamanho do `context` matriz.</span><span class="sxs-lookup"><span data-stu-id="147a5-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="147a5-108">[out no] Uma matriz de bytes que descrevem o contexto do thread.</span><span class="sxs-lookup"><span data-stu-id="147a5-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="147a5-109">O contexto Especifica a arquitetura do processador que o thread está em execução.</span><span class="sxs-lookup"><span data-stu-id="147a5-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="147a5-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="147a5-110">Remarks</span></span>  
 <span data-ttu-id="147a5-111">O depurador deve chamar esse método em vez de Win32 `GetThreadContext` método, porque o thread, na verdade, pode estar em um estado "capturado", no qual seu contexto foi temporariamente alterado.</span><span class="sxs-lookup"><span data-stu-id="147a5-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="147a5-112">Esse método deve ser usado somente quando um thread está no código nativo.</span><span class="sxs-lookup"><span data-stu-id="147a5-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="147a5-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) para segmentos no código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="147a5-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="147a5-114">Os dados retornados são uma estrutura de contexto para a plataforma atual.</span><span class="sxs-lookup"><span data-stu-id="147a5-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="147a5-115">Assim como ocorre com o Win32 `GetThreadContext` método, o chamador deve inicializar o `context` parâmetro antes de chamar esse método.</span><span class="sxs-lookup"><span data-stu-id="147a5-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="147a5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="147a5-116">Requirements</span></span>  
 <span data-ttu-id="147a5-117">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="147a5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="147a5-118">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="147a5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="147a5-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="147a5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="147a5-120">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="147a5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>