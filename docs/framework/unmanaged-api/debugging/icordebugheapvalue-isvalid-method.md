---
title: Método ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95532d6721467b482b1d79d611f8055b606bb4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413502"
---
# <a name="icordebugheapvalueisvalid-method"></a>Método ICorDebugHeapValue::IsValid
Obtém um valor que indica se o objeto representado por esse ICorDebugHeapValue é válido.  
  
 Esse método foi preterido no .NET Framework versão 2.0.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pbValid`  
 [out] Um ponteiro para um valor booliano que indica se esse valor no heap é válido.  
  
## <a name="remarks"></a>Comentários  
 O valor será inválido se ele tem sido recuperado pelo coletor de lixo.  
  
 Esse método foi substituído. No .NET Framework 2.0, todos os valores são válidos até [Icordebugcontroller](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) é chamado, no qual os valores são invalidados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
