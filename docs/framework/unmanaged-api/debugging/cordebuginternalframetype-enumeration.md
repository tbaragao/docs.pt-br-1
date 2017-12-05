---
title: "Enumeração CorDebugInternalFrameType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInternalFrameType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugInternalFrameType
helpviewer_keywords: CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b21e50c86a09092e7df65e5fddefb515f6838b2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="1a9d3-102">Enumeração CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="1a9d3-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="1a9d3-103">Identifica o tipo de quadro de pilha.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="1a9d3-104">Essa enumeração é usada pelo [Icordebuginternalframe](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a9d3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1a9d3-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="1a9d3-106">Membros</span><span class="sxs-lookup"><span data-stu-id="1a9d3-106">Members</span></span>  
  
|<span data-ttu-id="1a9d3-107">Membro</span><span class="sxs-lookup"><span data-stu-id="1a9d3-107">Member</span></span>|<span data-ttu-id="1a9d3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="1a9d3-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="1a9d3-109">Um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-109">A null value.</span></span> <span data-ttu-id="1a9d3-110">O `ICorDebugInternalFrame::GetFrameType` método nunca retorna esse valor.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="1a9d3-111">Um quadro de stub para gerenciado.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="1a9d3-112">Um quadro de stub não gerenciado para gerenciado.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="1a9d3-113">Uma transição entre domínios de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="1a9d3-114">Uma chamada de método leve.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="1a9d3-115">O início da avaliação de função.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="1a9d3-116">Uma chamada interna no common language runtime.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="1a9d3-117">O início de uma classe de inicialização.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="1a9d3-118">Uma exceção que é lançada.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="1a9d3-119">Um quadro usado para a segurança de acesso do código.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="1a9d3-120">O tempo de execução é um método de compilação JIT.</span><span class="sxs-lookup"><span data-stu-id="1a9d3-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a9d3-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a9d3-121">Requirements</span></span>  
 <span data-ttu-id="1a9d3-122">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a9d3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a9d3-123">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a9d3-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a9d3-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a9d3-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a9d3-125">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a9d3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a9d3-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1a9d3-126">See Also</span></span>  
 [<span data-ttu-id="1a9d3-127">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="1a9d3-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)