---
title: "Método ICorDebugAssembly::EnumerateModules"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.EnumerateModules
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28c6f2efe4a48c198bd64fa7f5665b97969dbc43
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="cd0f3-102">Método ICorDebugAssembly::EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="cd0f3-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="cd0f3-103">Obtém um enumerador para os módulos contidos no `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0f3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cd0f3-104">Syntax</span></span>  
  
```  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd0f3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cd0f3-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="cd0f3-106">[out] Um ponteiro para o endereço da interface ICorDebugModuleEnum que é o enumerador.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd0f3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd0f3-107">Requirements</span></span>  
 <span data-ttu-id="cd0f3-108">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd0f3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd0f3-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd0f3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd0f3-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd0f3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd0f3-111">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd0f3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>