---
title: Interface ICorDebugProcess6
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 222007d03d8ace00f97c01cf2a02f0dc293bbf78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="b05ad-102">Interface ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="b05ad-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="b05ad-103">Logicamente estende a interface ICorDebugProcess para habilitar recursos como decodificar os eventos de depuração gerenciados que são codificados em eventos de exceção nativo de depuração e divisão de módulo virtual.</span><span class="sxs-lookup"><span data-stu-id="b05ad-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b05ad-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b05ad-104">Methods</span></span>  
  
|<span data-ttu-id="b05ad-105">Método</span><span class="sxs-lookup"><span data-stu-id="b05ad-105">Method</span></span>|<span data-ttu-id="b05ad-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b05ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b05ad-107">Método DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="b05ad-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="b05ad-108">Decodifica eventos de depuração gerenciados que foram encapsulados na carga de eventos de depuração de exceção nativo especialmente criado.</span><span class="sxs-lookup"><span data-stu-id="b05ad-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="b05ad-109">Método EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="b05ad-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="b05ad-110">Habilita ou desabilita a divisão de módulo virtual.</span><span class="sxs-lookup"><span data-stu-id="b05ad-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="b05ad-111">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="b05ad-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="b05ad-112">Obtém informações sobre o código gerenciado em um endereço de código em particular.</span><span class="sxs-lookup"><span data-stu-id="b05ad-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="b05ad-113">Método GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="b05ad-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="b05ad-114">Fornece informações sobre funções exportadas de tempo de execução para ajudar a percorrer o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="b05ad-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="b05ad-115">Método MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="b05ad-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="b05ad-116">Altera o estado interno do depurado para que o método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> na biblioteca de classes .NET Framework retorne `true`.</span><span class="sxs-lookup"><span data-stu-id="b05ad-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="b05ad-117">Método ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="b05ad-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="b05ad-118">Notifica [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que o processo está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="b05ad-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b05ad-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="b05ad-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b05ad-120">A interface está disponível com o .NET Native somente.</span><span class="sxs-lookup"><span data-stu-id="b05ad-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="b05ad-121">Tentando chamar `QueryInterface` recuperar um ponteiro de interface retorna `E_NOINTERFACE` para cenários de ICorDebug fora do .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b05ad-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b05ad-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b05ad-122">Requirements</span></span>  
 <span data-ttu-id="b05ad-123">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b05ad-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b05ad-124">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b05ad-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b05ad-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b05ad-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b05ad-126">**Versões do .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b05ad-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05ad-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b05ad-127">See Also</span></span>  
 [<span data-ttu-id="b05ad-128">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="b05ad-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b05ad-129">Depuração</span><span class="sxs-lookup"><span data-stu-id="b05ad-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)