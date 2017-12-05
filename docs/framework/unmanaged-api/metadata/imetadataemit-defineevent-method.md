---
title: "Método IMetaDataEmit::DefineEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf790ce270565abaf1d91e54c9e3569a50ab3435
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="4d6c7-102">Método IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="4d6c7-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="4d6c7-103">Cria uma definição para um evento com a assinatura de metadados especificado e obtém um token a definição desse evento.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d6c7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d6c7-104">Syntax</span></span>  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d6c7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4d6c7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4d6c7-106">[in] O token para a interface ou classe de destino.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="4d6c7-107">Isso é uma `mdTypeDef` ou `mdTypeDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="4d6c7-108">[in] O nome do evento.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="4d6c7-109">[in] Sinalizadores de evento.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="4d6c7-110">[in] O token para a classe de evento.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-110">[in] The token for the event class.</span></span> <span data-ttu-id="4d6c7-111">Este é um `mdTypeDef`, um `mdTypeRef`, ou um `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="4d6c7-112">[in] O método usado para assinar o evento, ou nulo.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="4d6c7-113">[in] O método usado para cancelar a assinatura do evento, ou nulo.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="4d6c7-114">[in] O método usado (por uma classe derivada) para gerar o evento.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="4d6c7-115">[in] Uma matriz de tokens de outros métodos associados ao evento.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="4d6c7-116">A matriz é encerrada com um `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="4d6c7-117">[out] O token de metadados atribuído ao evento.</span><span class="sxs-lookup"><span data-stu-id="4d6c7-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d6c7-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d6c7-118">Requirements</span></span>  
 <span data-ttu-id="4d6c7-119">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d6c7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d6c7-120">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4d6c7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d6c7-121">**Biblioteca:** usado como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="4d6c7-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d6c7-122">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d6c7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6c7-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4d6c7-123">See Also</span></span>  
 [<span data-ttu-id="4d6c7-124">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4d6c7-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="4d6c7-125">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4d6c7-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)