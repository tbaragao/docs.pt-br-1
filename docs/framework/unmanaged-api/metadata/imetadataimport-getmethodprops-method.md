---
title: Método IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ca43ebc257ee4eb9d0ef17f3399e87c03b9f9c3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740002"
---
# <a name="imetadataimportgetmethodprops-method"></a>Método IMetaDataImport::GetMethodProps
Obtém o token de metadados associados com o método referenciado pelo MethodDef especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `mb`  
 [in] O token MethodDef que representa o método para retornar metadados.  
  
 `pClass`  
 [out] Um ponteiro para um token de TypeDef que representa o tipo que implementa o método.  
  
 `szMethod`  
 [out] Um ponteiro para um buffer que tem o nome do método.  
  
 `cchMethod`  
 [in] O tamanho solicitado do `szMethod`.  
  
 `pchMethod`  
 [out] Um ponteiro para o tamanho em caracteres largos da `szMethod`, ou, no caso de truncamento, o número real de caracteres largos no nome do método.  
  
 `pdwAttr`  
 [out] Um ponteiro para qualquer sinalizadores associados com o método.  
  
 `ppvSigBlob`  
 [out] Um ponteiro para a assinatura de metadados de binários do método.  
  
 `pcbSigBlob`  
 [out] Um ponteiro para o tamanho em bytes do `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Um ponteiro para o endereço virtual relativo do método.  
  
 `pdwImplFlags`  
 [out] Um ponteiro para os sinalizadores de implementação para o método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor.h  
  
 **Biblioteca:** Incluído como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Interface IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interface IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
