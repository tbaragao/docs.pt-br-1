---
title: "Método ICLRStrongName::StrongNameCompareAssemblies"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab69a0d0bb5894c2393e240b4f89b9a16dd98939
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="f12f1-102">Método ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="f12f1-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="f12f1-103">Determina se os dois assemblies diferem somente por suas assinaturas de nome forte.</span><span class="sxs-lookup"><span data-stu-id="f12f1-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f12f1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f12f1-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f12f1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f12f1-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="f12f1-106">[in] O caminho para o primeiro conjunto.</span><span class="sxs-lookup"><span data-stu-id="f12f1-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="f12f1-107">[in] O caminho para o segundo conjunto.</span><span class="sxs-lookup"><span data-stu-id="f12f1-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="f12f1-108">[out] Um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f12f1-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="f12f1-109">`SN_CMP_DIFFERENT`(0) - Especifica que os assemblies conterem dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="f12f1-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="f12f1-110">`SN_CMP_IDENTICAL`(1) - Especifica que os assemblies são exatamente iguais, incluindo suas assinaturas e a soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="f12f1-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="f12f1-111">`SN_CMP_SIGONLY`(2) - Especifica que os assemblies diferem somente por assinatura e soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="f12f1-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f12f1-112">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="f12f1-112">Return Value</span></span>  
 <span data-ttu-id="f12f1-113">`S_OK`Se o método foi concluída com êxito; Caso contrário, um valor HRESULT que indica uma falha (consulte [valores HRESULT comuns](http://go.microsoft.com/fwlink/?LinkId=213878) para obter uma lista).</span><span class="sxs-lookup"><span data-stu-id="f12f1-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f12f1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f12f1-114">Requirements</span></span>  
 <span data-ttu-id="f12f1-115">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f12f1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f12f1-116">**Cabeçalho:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f12f1-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f12f1-117">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="f12f1-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f12f1-118">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f12f1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f12f1-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="f12f1-119">Remarks</span></span>  
 <span data-ttu-id="f12f1-120">A assinatura de um assembly de nome forte consiste em nome de texto, versão, cultura e token de chave pública do assembly.</span><span class="sxs-lookup"><span data-stu-id="f12f1-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f12f1-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f12f1-121">See Also</span></span>  
 [<span data-ttu-id="f12f1-122">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f12f1-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)