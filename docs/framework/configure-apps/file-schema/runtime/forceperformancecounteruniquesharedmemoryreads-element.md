---
title: '&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c90799ed2db061e8f42cde79804789eb8d2da0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a><span data-ttu-id="06b01-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="06b01-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span></span>
<span data-ttu-id="06b01-103">Especifica se o PerfCounter.dll usa a configuração de registro CategoryOptions em um aplicativo do .NET Framework versão 1.1 para determinar se é preciso carregar dados do contador de desempenho da memória global ou da memória compartilhada especifica da categoria.</span><span class="sxs-lookup"><span data-stu-id="06b01-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="06b01-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="06b01-104">\<configuration></span></span>  
<span data-ttu-id="06b01-105">\<tempo de execução ></span><span class="sxs-lookup"><span data-stu-id="06b01-105">\<runtime></span></span>  
<span data-ttu-id="06b01-106">\<forcePerformanceCounterUniqueSharedMemoryReads ></span><span class="sxs-lookup"><span data-stu-id="06b01-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b01-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="06b01-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06b01-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="06b01-108">Attributes and Elements</span></span>  
 <span data-ttu-id="06b01-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="06b01-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06b01-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="06b01-110">Attributes</span></span>  
  
|<span data-ttu-id="06b01-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="06b01-111">Attribute</span></span>|<span data-ttu-id="06b01-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="06b01-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="06b01-113">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="06b01-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="06b01-114">Indica se PerfCounter.dll usa a configuração de registro CategoryOptions para determinar se deve carregar dados de contador de desempenho da memória compartilhada específicas de categoria ou memória global.</span><span class="sxs-lookup"><span data-stu-id="06b01-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="06b01-115">Atributo habilitado</span><span class="sxs-lookup"><span data-stu-id="06b01-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="06b01-116">Valor</span><span class="sxs-lookup"><span data-stu-id="06b01-116">Value</span></span>|<span data-ttu-id="06b01-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="06b01-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="06b01-118">PerfCounter.dll não usa o CategoryOptions essa configuração de registro é o padrão.</span><span class="sxs-lookup"><span data-stu-id="06b01-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="06b01-119">PerfCounter.dll usar a configuração de registro de CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="06b01-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06b01-120">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="06b01-120">Child Elements</span></span>  
 <span data-ttu-id="06b01-121">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="06b01-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06b01-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="06b01-122">Parent Elements</span></span>  
  
|<span data-ttu-id="06b01-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="06b01-123">Element</span></span>|<span data-ttu-id="06b01-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="06b01-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="06b01-125">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="06b01-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="06b01-126">Contém informações sobre associação do assembly e coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="06b01-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06b01-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="06b01-127">Remarks</span></span>  
 <span data-ttu-id="06b01-128">Em versões do .NET Framework antes do [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], correspondia a versão do PerfCounter.dll que foi carregado no tempo de execução que foi carregado no processo.</span><span class="sxs-lookup"><span data-stu-id="06b01-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="06b01-129">Se um computador tiver o .NET Framework versão 1.1 e o [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] instalado, um aplicativo do .NET Framework 1.1 carrega a versão do .NET Framework 1.1 do PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="06b01-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="06b01-130">Começando com o [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a versão instalada mais recente do PerfCounter.dll é carregada.</span><span class="sxs-lookup"><span data-stu-id="06b01-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="06b01-131">Isso significa que um aplicativo do .NET Framework 1.1 carregará o [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] versão do PerfCounter.dll se o [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="06b01-131">This means that a .NET Framework 1.1 application will load the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] version of PerfCounter.dll if the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] is installed on the computer.</span></span>  
  
 <span data-ttu-id="06b01-132">Começando com o [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], durante o consumo de contadores de desempenho, PerfCounter.dll verifica a entrada de registro CategoryOptions para cada provedor determinar se ele deve ler de memória compartilhada específicas de categoria ou a memória compartilhada global.</span><span class="sxs-lookup"><span data-stu-id="06b01-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="06b01-133">O PerfCounter.dll do .NET Framework 1.1 não lê essa entrada do registro, porque ele não está ciente de categoria específica memória compartilhada; ele sempre lê da memória compartilhada global.</span><span class="sxs-lookup"><span data-stu-id="06b01-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="06b01-134">Para compatibilidade com versões anteriores, o [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll não verifica a entrada de registro CategoryOptions quando executada em um aplicativo do .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="06b01-134">For backward compatibility, the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="06b01-135">Ele simplesmente usa a memória compartilhada global, como o PerfCounter.dll do .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="06b01-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="06b01-136">No entanto, você pode instruir o [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll para verificar a configuração do registro, permitindo que o `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.</span><span class="sxs-lookup"><span data-stu-id="06b01-136">However, you can instruct the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06b01-137">Habilitando o `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento não garante que a memória compartilhada específicas de categoria será usada.</span><span class="sxs-lookup"><span data-stu-id="06b01-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="06b01-138">Configuração habilitada para `true` só faz com que PerfCounter.dll referenciar a configuração de registro CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="06b01-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="06b01-139">A configuração padrão para CategoryOptions é usar a memória compartilhada específicas de categoria; No entanto, você pode alterar CategoryOptions para indicar que a memória compartilhada global deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="06b01-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="06b01-140">A chave do registro que contém a configuração CategoryOptions é HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="06b01-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="06b01-141">Por padrão, CategoryOptions é definido como 3, que instrui o PerfCounter.dll para uso de memória compartilhada específicas de categoria.</span><span class="sxs-lookup"><span data-stu-id="06b01-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="06b01-142">Se CategoryOptions for definido como 0, PerfCounter.dll usa a memória compartilhada global.</span><span class="sxs-lookup"><span data-stu-id="06b01-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="06b01-143">Dados da instância serão reutilizados somente se o nome da instância que está sendo criado é idêntico à instância que está sendo reutilizada.</span><span class="sxs-lookup"><span data-stu-id="06b01-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="06b01-144">Todas as versões será capazes de gravar na categoria.</span><span class="sxs-lookup"><span data-stu-id="06b01-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="06b01-145">Se CategoryOptions for definido como 1, a memória compartilhada global é usada, mas os dados de instância podem ser reutilizados se o nome da categoria é o mesmo comprimento que a categoria que está sendo reutilizado.</span><span class="sxs-lookup"><span data-stu-id="06b01-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="06b01-146">As configurações de 0 e 1 podem levar a vazamentos de memória e preenchimento de memória do contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="06b01-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06b01-147">Exemplo</span><span class="sxs-lookup"><span data-stu-id="06b01-147">Example</span></span>  
 <span data-ttu-id="06b01-148">O exemplo a seguir mostra como especificar se PerfCounter.dll devem fazer referência a entrada de registro CategoryOptions para determinar se deve usar a memória compartilhada específicas de categoria.</span><span class="sxs-lookup"><span data-stu-id="06b01-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06b01-149">Consulte também</span><span class="sxs-lookup"><span data-stu-id="06b01-149">See Also</span></span>  
 [<span data-ttu-id="06b01-150">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="06b01-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="06b01-151">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="06b01-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)