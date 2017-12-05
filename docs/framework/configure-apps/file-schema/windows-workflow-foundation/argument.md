---
title: '&lt;argumento&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3625d3bf6aa415c34b9c05bebdec390bcb51f69
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="ltargumentgt"></a><span data-ttu-id="29699-102">&lt;argumento&gt;</span><span class="sxs-lookup"><span data-stu-id="29699-102">&lt;argument&gt;</span></span>
<span data-ttu-id="29699-103">Um elemento de configuração que representa um argumento associado a uma consulta de estado de atividade.</span><span class="sxs-lookup"><span data-stu-id="29699-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="29699-104">Para obter mais informações sobre consultas de perfil de controle, consulte [perfis controle](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="29699-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="29699-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="29699-105">\<system.serviceModel></span></span>  
<span data-ttu-id="29699-106">\<controle ></span><span class="sxs-lookup"><span data-stu-id="29699-106">\<tracking></span></span>  
<span data-ttu-id="29699-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="29699-107">\<trackingProfile></span></span>  
<span data-ttu-id="29699-108">\<fluxo de trabalho ></span><span class="sxs-lookup"><span data-stu-id="29699-108">\<workflow></span></span>  
<span data-ttu-id="29699-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="29699-109">\<activityStateQueries></span></span>  
<span data-ttu-id="29699-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="29699-110">\<activityStateQuery></span></span>  
<span data-ttu-id="29699-111">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="29699-111">\<arguments></span></span>  
<span data-ttu-id="29699-112">\<argumento ></span><span class="sxs-lookup"><span data-stu-id="29699-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29699-113">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="29699-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29699-114">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="29699-114">Attributes and Elements</span></span>  
 <span data-ttu-id="29699-115">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="29699-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29699-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="29699-116">Attributes</span></span>  
  
|<span data-ttu-id="29699-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="29699-117">Attribute</span></span>|<span data-ttu-id="29699-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="29699-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29699-119">name</span><span class="sxs-lookup"><span data-stu-id="29699-119">name</span></span>|<span data-ttu-id="29699-120">Uma cadeia de caracteres que especifica o nome do argumento.</span><span class="sxs-lookup"><span data-stu-id="29699-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29699-121">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="29699-121">Child Elements</span></span>  
 <span data-ttu-id="29699-122">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="29699-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29699-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="29699-123">Parent Elements</span></span>  
  
|<span data-ttu-id="29699-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="29699-124">Element</span></span>|<span data-ttu-id="29699-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="29699-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29699-126">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="29699-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="29699-127">Uma coleção de argumentos associados a essa consulta de atividade.</span><span class="sxs-lookup"><span data-stu-id="29699-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29699-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="29699-128">Remarks</span></span>  
 <span data-ttu-id="29699-129">Um recurso exclusivo de um ActivityStateQuery é a capacidade de extrair dados para controlar a execução de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="29699-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="29699-130">Isso fornece contexto adicional ao acessar o rastreamento registra pós execução.</span><span class="sxs-lookup"><span data-stu-id="29699-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="29699-131">Você pode usar o [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos para extrair qualquer variável ou argumento de qualquer atividade em um fluxo de trabalho. O exemplo a seguir mostra uma consulta de estado de atividade que extrai os argumentos e variáveis quando a atividade `Closed` registro de rastreamento é emitido.</span><span class="sxs-lookup"><span data-stu-id="29699-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="29699-132">Variáveis e argumentos pode ser extraídos apenas com um ActivityStateRecord e, portanto, se inscreveu em um controle de perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="29699-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29699-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="29699-133">See Also</span></span>  
 <span data-ttu-id="29699-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="29699-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="29699-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="29699-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="29699-136">Acompanhamento e rastreamento de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="29699-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="29699-137">Acompanhando perfis</span><span class="sxs-lookup"><span data-stu-id="29699-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)