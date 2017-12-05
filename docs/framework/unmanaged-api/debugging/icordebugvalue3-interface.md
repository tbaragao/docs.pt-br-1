---
title: Interface ICorDebugValue3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3
helpviewer_keywords: ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3948a4c404036235767f8de6747966709b75bc4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="266d0-102">Interface ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="266d0-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="266d0-103">Estende as interfaces "ICorDebugValue" e "ICorDebugValue2" para oferecer suporte para matrizes que são maiores do que 2 GB.</span><span class="sxs-lookup"><span data-stu-id="266d0-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="266d0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="266d0-104">Methods</span></span>  
  
|<span data-ttu-id="266d0-105">Método</span><span class="sxs-lookup"><span data-stu-id="266d0-105">Method</span></span>|<span data-ttu-id="266d0-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="266d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="266d0-107">Método GetSize64</span><span class="sxs-lookup"><span data-stu-id="266d0-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="266d0-108">Obtém o tamanho, em bytes, isso `ICorDebugValue3` objeto.</span><span class="sxs-lookup"><span data-stu-id="266d0-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="266d0-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="266d0-109">Remarks</span></span>  
 <span data-ttu-id="266d0-110">O [Icordebugvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) método retorna um tamanho de objeto que varia de 0 a 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="266d0-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="266d0-111">No [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], o tamanho das matrizes pode exceder 2 GB.</span><span class="sxs-lookup"><span data-stu-id="266d0-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="266d0-112">O `ICorDebugValue3` interface permite que você determine o tamanho desses conjuntos.</span><span class="sxs-lookup"><span data-stu-id="266d0-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="266d0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="266d0-113">Requirements</span></span>  
 <span data-ttu-id="266d0-114">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="266d0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="266d0-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="266d0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="266d0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="266d0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="266d0-117">**Versões do .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="266d0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266d0-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="266d0-118">See Also</span></span>  
    
    
 [<span data-ttu-id="266d0-119">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="266d0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="266d0-120">Depuração</span><span class="sxs-lookup"><span data-stu-id="266d0-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)