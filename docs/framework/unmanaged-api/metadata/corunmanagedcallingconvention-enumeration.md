---
title: "Enumeração CorUnmanagedCallingConvention"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorUnmanagedCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnmanagedCallingConvention
helpviewer_keywords: CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f66cb036de8450d4c1b3431b92487260956d47f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="68dc9-102">Enumeração CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="68dc9-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="68dc9-103">Especifica as convenções de chamada para código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="68dc9-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68dc9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68dc9-104">Syntax</span></span>  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="68dc9-105">Membros</span><span class="sxs-lookup"><span data-stu-id="68dc9-105">Members</span></span>  
  
|<span data-ttu-id="68dc9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="68dc9-106">Member</span></span>|<span data-ttu-id="68dc9-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="68dc9-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="68dc9-108">A convenção de chamada de idioma de C.</span><span class="sxs-lookup"><span data-stu-id="68dc9-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="68dc9-109">A convenção de chamada padrão.</span><span class="sxs-lookup"><span data-stu-id="68dc9-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="68dc9-110">A "this" convenção de chamada.</span><span class="sxs-lookup"><span data-stu-id="68dc9-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="68dc9-111">A convenção de chamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="68dc9-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="68dc9-112">Não usado.</span><span class="sxs-lookup"><span data-stu-id="68dc9-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="68dc9-113">Não usado.</span><span class="sxs-lookup"><span data-stu-id="68dc9-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="68dc9-114">Não usado.</span><span class="sxs-lookup"><span data-stu-id="68dc9-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="68dc9-115">Não usado.</span><span class="sxs-lookup"><span data-stu-id="68dc9-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68dc9-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="68dc9-116">Remarks</span></span>  
 <span data-ttu-id="68dc9-117">O CLR não dá suporte a convenção de chamada "rápida" no .NET Framework versão 1.0.</span><span class="sxs-lookup"><span data-stu-id="68dc9-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68dc9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68dc9-118">Requirements</span></span>  
 <span data-ttu-id="68dc9-119">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68dc9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68dc9-120">**Cabeçalho:** Corhdr</span><span class="sxs-lookup"><span data-stu-id="68dc9-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="68dc9-121">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68dc9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68dc9-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="68dc9-122">See Also</span></span>  
 [<span data-ttu-id="68dc9-123">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="68dc9-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)