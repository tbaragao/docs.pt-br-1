---
title: Método ICorDebugAssembly::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe587f6356eec861c39c9eb0aa0b6476e0b9a232
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407513"
---
# <a name="icordebugassemblygetname-method"></a>Método ICorDebugAssembly::GetName
Obtém o nome do assembly que isso `ICorDebugAssembly` instância representa.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `cchName`  
 [in] O tamanho do `szName` matriz.  
  
 `pcchName`  
 [out] Um ponteiro para um inteiro que especifica o comprimento real do nome.  
  
 `szName`  
 [out] Uma matriz que armazena o nome.  
  
## <a name="remarks"></a>Comentários  
 O `GetName` método retorna o nome de arquivo e caminho completo do assembly.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
