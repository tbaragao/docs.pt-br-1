---
title: "Função CreateInstanceEnumWmi (referência de API não gerenciada)"
description: "A função CreateInstanceEnumWmi retorna um enumerador que contém instâncias de uma classe especificada que atendem aos critérios de seleção."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateInstanceEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateInstanceEnumWmi
helpviewer_keywords: CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19a4102796da7a5692eb5b9b459a6a95ff7409f9
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="68d27-103">Função CreateInstanceEnumWmi</span><span class="sxs-lookup"><span data-stu-id="68d27-103">CreateInstanceEnumWmi function</span></span>
<span data-ttu-id="68d27-104">Retorna um enumerador que retorna as instâncias de uma classe especificada que atendem aos critérios de seleção especificada.</span><span class="sxs-lookup"><span data-stu-id="68d27-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="68d27-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68d27-105">Syntax</span></span>  
  
```  
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="68d27-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="68d27-106">Parameters</span></span>

`strFilter`    
<span data-ttu-id="68d27-107">[in] O nome da classe para a qual as instâncias são desejadas.</span><span class="sxs-lookup"><span data-stu-id="68d27-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="68d27-108">O parâmetro não pode ser `null`.</span><span class="sxs-lookup"><span data-stu-id="68d27-108">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="68d27-109">[in] Uma combinação de sinalizadores que afetam o comportamento dessa função.</span><span class="sxs-lookup"><span data-stu-id="68d27-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="68d27-110">Os seguintes valores são definidos no *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="68d27-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="68d27-111">Constante</span><span class="sxs-lookup"><span data-stu-id="68d27-111">Constant</span></span>  |<span data-ttu-id="68d27-112">Valor</span><span class="sxs-lookup"><span data-stu-id="68d27-112">Value</span></span>  |<span data-ttu-id="68d27-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="68d27-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="68d27-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="68d27-114">0x20000</span></span> | <span data-ttu-id="68d27-115">Se o conjunto, a função recupera os qualificadores aperfeiçoados armazenados no namespace localizado da localidade da conexão atual.</span><span class="sxs-lookup"><span data-stu-id="68d27-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="68d27-116">Se não for definido, a função recupera somente os qualificadores armazenados no namespace de imediato.</span><span class="sxs-lookup"><span data-stu-id="68d27-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="68d27-117">0</span><span class="sxs-lookup"><span data-stu-id="68d27-117">0</span></span> | <span data-ttu-id="68d27-118">A enumeração inclui todas as subclasses na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="68d27-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="68d27-119">1</span><span class="sxs-lookup"><span data-stu-id="68d27-119">1</span></span> | <span data-ttu-id="68d27-120">A enumeração inclui somente puras instâncias dessa classe e exclui todas as instâncias das subclasses que fornecem a propriedade não foi encontrada nesta classe.</span><span class="sxs-lookup"><span data-stu-id="68d27-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="68d27-121">0x10</span><span class="sxs-lookup"><span data-stu-id="68d27-121">0x10</span></span> | <span data-ttu-id="68d27-122">O sinalizador faz com que uma chamada semi-síncrona.</span><span class="sxs-lookup"><span data-stu-id="68d27-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="68d27-123">0x20</span><span class="sxs-lookup"><span data-stu-id="68d27-123">0x20</span></span> | <span data-ttu-id="68d27-124">A função retorna um enumerador de somente avanço.</span><span class="sxs-lookup"><span data-stu-id="68d27-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="68d27-125">Normalmente, os enumeradores de somente avanço são mais rápidos e usam menos memória do que os enumeradores convencionais, mas não permitem chamadas para [Clone](clone.md).</span><span class="sxs-lookup"><span data-stu-id="68d27-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="68d27-126">0</span><span class="sxs-lookup"><span data-stu-id="68d27-126">0</span></span> | <span data-ttu-id="68d27-127">WMI retém ponteiros para objetos de enumration até que eles sejam liberados.</span><span class="sxs-lookup"><span data-stu-id="68d27-127">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="68d27-128">Os sinalizadores recomendados são `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` para melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="68d27-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="68d27-129">[in] Normalmente, esse valor é `null`.</span><span class="sxs-lookup"><span data-stu-id="68d27-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="68d27-130">Caso contrário, é um ponteiro para um [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instância pode ser usada pelo provedor que está fornecendo as instâncias solicitadas.</span><span class="sxs-lookup"><span data-stu-id="68d27-130">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`  
<span data-ttu-id="68d27-131">[out] Recebe o ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="68d27-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="68d27-132">[in] O nível de autorização.</span><span class="sxs-lookup"><span data-stu-id="68d27-132">[in] The authorization level.</span></span>

<span data-ttu-id="68d27-133">`impLevel`[in] O nível de representação.</span><span class="sxs-lookup"><span data-stu-id="68d27-133">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="68d27-134">[in] Um ponteiro para um [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objeto que representa o namespace atual.</span><span class="sxs-lookup"><span data-stu-id="68d27-134">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="68d27-135">[in] O nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="68d27-135">[in] The user name.</span></span> <span data-ttu-id="68d27-136">Consulte o [ConnectServerWmi](connectserverwmi.md) função para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="68d27-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="68d27-137">[in] A senha.</span><span class="sxs-lookup"><span data-stu-id="68d27-137">[in] The password.</span></span> <span data-ttu-id="68d27-138">Consulte o [ConnectServerWmi](connectserverwmi.md) função para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="68d27-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="68d27-139">[in] O nome de domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="68d27-139">[in] The domain name of the user.</span></span> <span data-ttu-id="68d27-140">Consulte o [ConnectServerWmi](connectserverwmi.md) função para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="68d27-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="68d27-141">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="68d27-141">Return value</span></span>

<span data-ttu-id="68d27-142">Os seguintes valores retornados por essa função são definidos no *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="68d27-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="68d27-143">Constante</span><span class="sxs-lookup"><span data-stu-id="68d27-143">Constant</span></span>  |<span data-ttu-id="68d27-144">Valor</span><span class="sxs-lookup"><span data-stu-id="68d27-144">Value</span></span>  |<span data-ttu-id="68d27-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="68d27-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="68d27-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="68d27-146">0x80041003</span></span> | <span data-ttu-id="68d27-147">O usuário não tem permissão para exibir as instâncias da classe especificada.</span><span class="sxs-lookup"><span data-stu-id="68d27-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="68d27-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="68d27-148">0x80041001</span></span> | <span data-ttu-id="68d27-149">Ocorreu um erro não especificado.</span><span class="sxs-lookup"><span data-stu-id="68d27-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="68d27-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="68d27-150">0x80041010</span></span> | <span data-ttu-id="68d27-151">`strFilter` não existe.</span><span class="sxs-lookup"><span data-stu-id="68d27-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="68d27-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="68d27-152">0x80041008</span></span> | <span data-ttu-id="68d27-153">Um parâmetro não é válido.</span><span class="sxs-lookup"><span data-stu-id="68d27-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="68d27-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="68d27-154">0x80041006</span></span> | <span data-ttu-id="68d27-155">Não há memória suficiente está disponível para concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="68d27-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="68d27-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="68d27-156">0x80041033</span></span> | <span data-ttu-id="68d27-157">WMI foi provavelmente interrompido e reiniciar.</span><span class="sxs-lookup"><span data-stu-id="68d27-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="68d27-158">Chamar [ConnectServerWmi](connectserverwmi.md) novamente.</span><span class="sxs-lookup"><span data-stu-id="68d27-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="68d27-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="68d27-159">0x80041015</span></span> | <span data-ttu-id="68d27-160">O link RPC (chamada) de procedimento remoto entre o processo atual e a WMI falhou.</span><span class="sxs-lookup"><span data-stu-id="68d27-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="68d27-161">0</span><span class="sxs-lookup"><span data-stu-id="68d27-161">0</span></span> | <span data-ttu-id="68d27-162">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="68d27-162">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="68d27-163">Comentários</span><span class="sxs-lookup"><span data-stu-id="68d27-163">Remarks</span></span>

<span data-ttu-id="68d27-164">Essa função encapsula uma chamada para o [Createclassenum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="68d27-164">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="68d27-165">Observe que o enumerador retornado pode ter zero elementos.</span><span class="sxs-lookup"><span data-stu-id="68d27-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="68d27-166">Se a chamada de função falhar, você pode obter informações adicionais sobre erros chamando o [GetErrorInfo](geterrorinfo.md) função.</span><span class="sxs-lookup"><span data-stu-id="68d27-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="68d27-167">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68d27-167">Requirements</span></span>  
 <span data-ttu-id="68d27-168">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68d27-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68d27-169">**Cabeçalho:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="68d27-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="68d27-170">**Versões do .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="68d27-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d27-171">Consulte também</span><span class="sxs-lookup"><span data-stu-id="68d27-171">See also</span></span>  
[<span data-ttu-id="68d27-172">WMI e contadores de desempenho (referência de API não gerenciada)</span><span class="sxs-lookup"><span data-stu-id="68d27-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)