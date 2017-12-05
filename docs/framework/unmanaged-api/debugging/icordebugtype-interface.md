---
title: ICorDebugType Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType
helpviewer_keywords: ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a25e72766e6647f820c9871e989d4b24db0bf26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtype-interface1"></a><span data-ttu-id="c8bce-102">ICorDebugType Interface1</span><span class="sxs-lookup"><span data-stu-id="c8bce-102">ICorDebugType Interface1</span></span>
<span data-ttu-id="c8bce-103">Representa um tipo básico ou complexo (que é, definido pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="c8bce-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="c8bce-104">Se o tipo for genérico, `ICorDebugType` representará o tipo genérico instanciado.</span><span class="sxs-lookup"><span data-stu-id="c8bce-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8bce-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c8bce-105">Methods</span></span>  
  
|<span data-ttu-id="c8bce-106">Método</span><span class="sxs-lookup"><span data-stu-id="c8bce-106">Method</span></span>|<span data-ttu-id="c8bce-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8bce-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8bce-108">Método EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="c8bce-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="c8bce-109">Obtém um ponteiro de interface para um ICorDebugTypeEnum que faz referência genérica <xref:System.Type> parâmetros da classe referenciada por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c8bce-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="c8bce-110">Método GetBase</span><span class="sxs-lookup"><span data-stu-id="c8bce-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="c8bce-111">Obtém um ponteiro de interface para um `ICorDebugType` que referencia a classe base da classe referenciada por este `ICorDebugType`, se houver.</span><span class="sxs-lookup"><span data-stu-id="c8bce-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="c8bce-112">Método GetClass</span><span class="sxs-lookup"><span data-stu-id="c8bce-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="c8bce-113">Obtém um ponteiro de interface para um ICorDebugClass que referencia o construtor com tipo deste `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c8bce-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="c8bce-114">Método GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="c8bce-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="c8bce-115">Obtém um ponteiro de interface para um `ICorDebugType` que referencia o primeiro genérico <xref:System.Type> parâmetro para o construtor da classe referenciada por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c8bce-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="c8bce-116">Método GetRank</span><span class="sxs-lookup"><span data-stu-id="c8bce-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="c8bce-117">Obtém o número de dimensões em um tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="c8bce-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="c8bce-118">Método GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="c8bce-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="c8bce-119">Obtém um ponteiro de interface para um ICorDebugValue que contém o valor do campo estático referenciado pelo campo especificado token no quadro de pilha especificada.</span><span class="sxs-lookup"><span data-stu-id="c8bce-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="c8bce-120">Método GetType</span><span class="sxs-lookup"><span data-stu-id="c8bce-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="c8bce-121">Obtém um valor de CorElementType que descreve o tipo nativo do common language runtime <xref:System.Type> referenciada por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c8bce-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8bce-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="c8bce-122">Remarks</span></span>  
 <span data-ttu-id="c8bce-123">Se o tipo for genérico, `ICorDebugClass` representa o tipo instanciado.</span><span class="sxs-lookup"><span data-stu-id="c8bce-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="c8bce-124">O `ICorDebugType` interface representa um tipo genérico instanciado.</span><span class="sxs-lookup"><span data-stu-id="c8bce-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="c8bce-125">Por exemplo, tabela de hash\<K, V > seria representado por `ICorDebugClass`, enquanto Hashtable\<Int32, a cadeia de caracteres > seria representado por `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c8bce-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="c8bce-126">Tipos genéricos não são representados por ambos `ICorDebugClass` e `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c8bce-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="c8bce-127">A segunda interface foi introduzida no .NET Framework versão 2.0 para lidar com uma instância de tipo.</span><span class="sxs-lookup"><span data-stu-id="c8bce-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8bce-128">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="c8bce-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8bce-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8bce-129">Requirements</span></span>  
 <span data-ttu-id="c8bce-130">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8bce-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8bce-131">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8bce-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8bce-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8bce-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8bce-133">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8bce-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bce-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c8bce-134">See Also</span></span>  
 [<span data-ttu-id="c8bce-135">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="c8bce-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)