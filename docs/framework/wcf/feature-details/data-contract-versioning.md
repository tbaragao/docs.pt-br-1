---
title: "Controle de versão de contrato de dados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- versioning [WCF], data contracts
- versioning [WCF]
- data contracts [WCF], versioning
ms.assetid: 4a0700cb-5f5f-4137-8705-3a3ecf06461f
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68d9d153127f3f34c6546cef9f2b3ab5fc668899
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="data-contract-versioning"></a><span data-ttu-id="da660-102">Controle de versão de contrato de dados</span><span class="sxs-lookup"><span data-stu-id="da660-102">Data Contract Versioning</span></span>
<span data-ttu-id="da660-103">Como desenvolvem aplicativos, você também terá que alterar o uso de serviços de contratos de dados.</span><span class="sxs-lookup"><span data-stu-id="da660-103">As applications evolve, you may also have to change the data contracts the services use.</span></span> <span data-ttu-id="da660-104">Este tópico explica como contratos de dados de versão.</span><span class="sxs-lookup"><span data-stu-id="da660-104">This topic explains how to version data contracts.</span></span> <span data-ttu-id="da660-105">Este tópico descreve os mecanismos de controle de versão do contrato de dados.</span><span class="sxs-lookup"><span data-stu-id="da660-105">This topic describes the data contract versioning mechanisms.</span></span> <span data-ttu-id="da660-106">Para obter uma visão geral completa e orientação prescritiva do controle de versão, consulte [práticas recomendadas: controle de versão de contrato de dados](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="da660-106">For a complete overview and prescriptive versioning guidance, see [Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span></span>  
  
## <a name="breaking-vs-nonbreaking-changes"></a><span data-ttu-id="da660-107">Quebrando vs. Alterações incondicionais</span><span class="sxs-lookup"><span data-stu-id="da660-107">Breaking vs. Nonbreaking Changes</span></span>  
 <span data-ttu-id="da660-108">As alterações a um contrato de dados podem quebrar ou incondicional.</span><span class="sxs-lookup"><span data-stu-id="da660-108">Changes to a data contract can be breaking or nonbreaking.</span></span> <span data-ttu-id="da660-109">Quando um contrato de dados é alterado de forma incondicional, um aplicativo usando a versão mais antiga do contrato pode se comunicar com um aplicativo usando a versão mais recente e um aplicativo usando a versão mais recente do contrato pode se comunicar com um aplicativo usando a versão mais antiga.</span><span class="sxs-lookup"><span data-stu-id="da660-109">When a data contract is changed in a nonbreaking way, an application using the older version of the contract can communicate with an application using the newer version, and an application using the newer version of the contract can communicate with an application using the older version.</span></span> <span data-ttu-id="da660-110">Por outro lado, uma alteração significativa impede a comunicação em uma ou ambas as direções.</span><span class="sxs-lookup"><span data-stu-id="da660-110">On the other hand, a breaking change prevents communication in one or both directions.</span></span>  
  
 <span data-ttu-id="da660-111">As alterações para um tipo que não afetam como são transmitida e recebida são incondicional.</span><span class="sxs-lookup"><span data-stu-id="da660-111">Any changes to a type that do not affect how it is transmitted and received are nonbreaking.</span></span> <span data-ttu-id="da660-112">Essas alterações não alteram o contrato de dados, somente o tipo subjacente.</span><span class="sxs-lookup"><span data-stu-id="da660-112">Such changes do not change the data contract, only the underlying type.</span></span> <span data-ttu-id="da660-113">Por exemplo, você pode alterar o nome de um campo de forma incondicional, se você definir o <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> propriedade o <xref:System.Runtime.Serialization.DataMemberAttribute> para o nome da versão mais antigo.</span><span class="sxs-lookup"><span data-stu-id="da660-113">For example, you can change the name of a field in a nonbreaking way if you then set the <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> to the older version name.</span></span> <span data-ttu-id="da660-114">O código a seguir mostra a versão 1 de um contrato de dados.</span><span class="sxs-lookup"><span data-stu-id="da660-114">The following code shows version 1 of a data contract.</span></span>  
  
 [!code-csharp[C_DataContractVersioning#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#1)]
 [!code-vb[C_DataContractVersioning#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#1)]  
  
 <span data-ttu-id="da660-115">O código a seguir mostra uma alteração incondicional.</span><span class="sxs-lookup"><span data-stu-id="da660-115">The following code shows a nonbreaking change.</span></span>  
  
 [!code-csharp[C_DataContractVersioning#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#2)]
 [!code-vb[C_DataContractVersioning#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#2)]  
  
 <span data-ttu-id="da660-116">Algumas alterações modifiquem os dados transmitidos, mas podem ou não podem ser recentes.</span><span class="sxs-lookup"><span data-stu-id="da660-116">Some changes do modify the transmitted data, but may or may not be breaking.</span></span> <span data-ttu-id="da660-117">As seguintes alterações sempre são significativas:</span><span class="sxs-lookup"><span data-stu-id="da660-117">The following changes are always breaking:</span></span>  
  
-   <span data-ttu-id="da660-118">Alterando o <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> ou <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> valor de um contrato de dados.</span><span class="sxs-lookup"><span data-stu-id="da660-118">Changing the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> or <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> value of a data contract.</span></span>  
  
-   <span data-ttu-id="da660-119">Alterando a ordem dos membros de dados usando o <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> propriedade o <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="da660-119">Changing the order of data members by using the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute>.</span></span>  
  
-   <span data-ttu-id="da660-120">Renomeando um membro de dados.</span><span class="sxs-lookup"><span data-stu-id="da660-120">Renaming a data member.</span></span>  
  
-   <span data-ttu-id="da660-121">Alterando o contrato de dados de um membro de dados.</span><span class="sxs-lookup"><span data-stu-id="da660-121">Changing the data contract of a data member.</span></span> <span data-ttu-id="da660-122">Por exemplo, alterando o tipo de membro de dados de um inteiro como uma cadeia de caracteres ou de um tipo com um contrato de dados denominado "Customer" para um tipo com um contrato de dados denominado "Pessoa".</span><span class="sxs-lookup"><span data-stu-id="da660-122">For example, changing the type of data member from an integer to a string, or from a type with a data contract named "Customer" to a type with a data contract named "Person".</span></span>  
  
 <span data-ttu-id="da660-123">As alterações a seguir também são possíveis.</span><span class="sxs-lookup"><span data-stu-id="da660-123">The following changes are also possible.</span></span>  
  
## <a name="adding-and-removing-data-members"></a><span data-ttu-id="da660-124">Adicionando e removendo membros de dados</span><span class="sxs-lookup"><span data-stu-id="da660-124">Adding and Removing Data Members</span></span>  
 <span data-ttu-id="da660-125">Na maioria dos casos, adicionar ou remover um membro de dados não é uma alteração significativa, a menos que exigem a validade de esquema estrita (novas instâncias validar em relação ao esquema antigo).</span><span class="sxs-lookup"><span data-stu-id="da660-125">In most cases, adding or removing a data member is not a breaking change, unless you require strict schema validity (new instances validating against the old schema).</span></span>  
  
 <span data-ttu-id="da660-126">Quando um tipo com um campo extra é desserializado em um tipo com um campo ausente, as informações adicionais serão ignoradas.</span><span class="sxs-lookup"><span data-stu-id="da660-126">When a type with an extra field is deserialized into a type with a missing field, the extra information is ignored.</span></span> <span data-ttu-id="da660-127">(Também pode ser armazenada para fins de ciclo; para obter mais informações, consulte [contratos de dados compatíveis por encaminhamento](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)).</span><span class="sxs-lookup"><span data-stu-id="da660-127">(It may also be stored for round-tripping purposes; for more information, see [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)).</span></span>  
  
 <span data-ttu-id="da660-128">Quando um tipo com um campo ausente é desserializado em um tipo com um campo adicional, o campo extra for deixado em seu valor padrão, zero geralmente ou `null`.</span><span class="sxs-lookup"><span data-stu-id="da660-128">When a type with a missing field is deserialized into a type with an extra field, the extra field is left at its default value, usually zero or `null`.</span></span> <span data-ttu-id="da660-129">(O valor padrão pode ser alterado; para obter mais informações, consulte [retornos de chamada de serialização tolerantes à versão](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md).)</span><span class="sxs-lookup"><span data-stu-id="da660-129">(The default value may be changed; for more information, see [Version-Tolerant Serialization Callbacks](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md).)</span></span>  
  
 <span data-ttu-id="da660-130">Por exemplo, você pode usar o `CarV1` classe em um cliente e o `CarV2` classe em um serviço, ou você pode usar o `CarV1` classe em um serviço e o `CarV2` classe em um cliente.</span><span class="sxs-lookup"><span data-stu-id="da660-130">For example, you can use the `CarV1` class on a client and the `CarV2` class on a service, or you can use the `CarV1` class on a service and the `CarV2` class on a client.</span></span>  
  
 [!code-csharp[C_DataContractVersioning#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#3)]
 [!code-vb[C_DataContractVersioning#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#3)]  
  
 <span data-ttu-id="da660-131">O ponto de extremidade de versão 2 com êxito pode enviar dados para o ponto de extremidade de versão 1.</span><span class="sxs-lookup"><span data-stu-id="da660-131">The version 2 endpoint can successfully send data to the version 1 endpoint.</span></span> <span data-ttu-id="da660-132">Serializar a versão 2 do `Car` contrato de dados gera XML semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="da660-132">Serializing version 2 of the `Car` data contract yields XML similar to the following.</span></span>  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
    <HorsePower>300</HorsePower>  
</Car>  
```  
  
 <span data-ttu-id="da660-133">O mecanismo de desserialização em V1 não localizar um membro de dados correspondente para o `HorsePower` campo e, em seguida, descarta os dados.</span><span class="sxs-lookup"><span data-stu-id="da660-133">The deserialization engine on V1 does not find a matching data member for the `HorsePower` field, and discards that data.</span></span>  
  
 <span data-ttu-id="da660-134">Além disso, o ponto de extremidade de versão 1 pode enviar dados para o ponto de extremidade de versão 2.</span><span class="sxs-lookup"><span data-stu-id="da660-134">Also, the version 1 endpoint can send data to the version 2 endpoint.</span></span> <span data-ttu-id="da660-135">Serializar a versão 1 do `Car` contrato de dados gera XML semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="da660-135">Serializing version 1 of the `Car` data contract yields XML similar to the following.</span></span>  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
</Car>  
```  
  
 <span data-ttu-id="da660-136">O desserializador versão 2 não sabe o que definir o `HorsePower` campo, porque não há nenhum dado correspondentes no XML de entrada.</span><span class="sxs-lookup"><span data-stu-id="da660-136">The version 2 deserializer does not know what to set the `HorsePower` field to, because there is no matching data in the incoming XML.</span></span> <span data-ttu-id="da660-137">Em vez disso, o campo é definido como o valor padrão de 0.</span><span class="sxs-lookup"><span data-stu-id="da660-137">Instead, the field is set to the default value of 0.</span></span>  
  
## <a name="required-data-members"></a><span data-ttu-id="da660-138">Membros de dados necessários</span><span class="sxs-lookup"><span data-stu-id="da660-138">Required Data Members</span></span>  
 <span data-ttu-id="da660-139">Um membro de dados pode ser marcado como sendo necessária definindo o <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> propriedade o <xref:System.Runtime.Serialization.DataMemberAttribute> para `true`.</span><span class="sxs-lookup"><span data-stu-id="da660-139">A data member may be marked as being required by setting the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> to `true`.</span></span> <span data-ttu-id="da660-140">Se necessárias estão faltando dados durante a desserialização, uma exceção será lançada em vez de definir o membro de dados para o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="da660-140">If required data is missing while deserializing, an exception is thrown instead of setting the data member to its default value.</span></span>  
  
 <span data-ttu-id="da660-141">Adicionando um membro de dados necessários é uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="da660-141">Adding a required data member is a breaking change.</span></span> <span data-ttu-id="da660-142">Ou seja, o tipo mais recente ainda pode ser enviado aos pontos de extremidade com o tipo mais antigo, mas não o oposto.</span><span class="sxs-lookup"><span data-stu-id="da660-142">That is, the newer type can still be sent to endpoints with the older type, but not the other way around.</span></span> <span data-ttu-id="da660-143">Remover um membro de dados que foi marcado como necessária em qualquer versão anterior é também uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="da660-143">Removing a data member that was marked as required in any prior version is also a breaking change.</span></span>  
  
 <span data-ttu-id="da660-144">Alterando o <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> valor de propriedade de `true` para `false` não recentes, mas mudando de `false` para `true` pode ser quebrar se todas as versões anteriores do tipo não tem o membro de dados em questão.</span><span class="sxs-lookup"><span data-stu-id="da660-144">Changing the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property value from `true` to `false` is not breaking, but changing it from `false` to `true` may be breaking if any prior versions of the type do not have the data member in question.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da660-145">Embora o <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> está definida como `true`, os dados de entrada podem ser nulos ou zero e um tipo devem estar preparado para lidar com essa possibilidade.</span><span class="sxs-lookup"><span data-stu-id="da660-145">Although the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property is set to `true`, the incoming data may be null or zero, and a type must be prepared to handle this possibility.</span></span> <span data-ttu-id="da660-146">Não use <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> como um mecanismo de segurança para ajudar a proteger os dados de entrada incorretos.</span><span class="sxs-lookup"><span data-stu-id="da660-146">Do not use <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> as a security mechanism to protect against bad incoming data.</span></span>  
  
## <a name="omitted-default-values"></a><span data-ttu-id="da660-147">Valores padrão omitido</span><span class="sxs-lookup"><span data-stu-id="da660-147">Omitted Default Values</span></span>  
 <span data-ttu-id="da660-148">É possível (embora não recomendado) para definir o `EmitDefaultValue` propriedade no atributo DataMemberAttribute para `false`, conforme descrito em [valores de padrão de membro de dados](../../../../docs/framework/wcf/feature-details/data-member-default-values.md).</span><span class="sxs-lookup"><span data-stu-id="da660-148">It is possible (although not recommended) to set the `EmitDefaultValue` property on the DataMemberAttribute attribute to `false`, as described in [Data Member Default Values](../../../../docs/framework/wcf/feature-details/data-member-default-values.md).</span></span> <span data-ttu-id="da660-149">Se essa configuração for `false`, o membro de dados não será emitido se ele for definido como seu valor padrão (geralmente nulo ou zero).</span><span class="sxs-lookup"><span data-stu-id="da660-149">If this setting is `false`, the data member will not be emitted if it is set to its default value (usually null or zero).</span></span> <span data-ttu-id="da660-150">Isso não é compatível com membros de dados necessários em versões diferentes de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="da660-150">This is not compatible with required data members in different versions in two ways:</span></span>  
  
-   <span data-ttu-id="da660-151">Um contrato de dados com um membro de dados que é necessário em uma versão não pode receber padrão (null ou zero) dados de uma versão diferente no qual o membro de dados tem `EmitDefaultValue` definido como `false`.</span><span class="sxs-lookup"><span data-stu-id="da660-151">A data contract with a data member that is required in one version cannot receive default (null or zero) data from a different version in which the data member has `EmitDefaultValue` set to `false`.</span></span>  
  
-   <span data-ttu-id="da660-152">Um membro de dados necessários que tem `EmitDefaultValue` definida como `false` não pode ser usado para serializar o padrão (null ou zero) valor, mas pode receber esse valor na desserialização.</span><span class="sxs-lookup"><span data-stu-id="da660-152">A required data member that has `EmitDefaultValue` set to `false` cannot be used to serialize its default (null or zero) value, but can receive such a value on deserialization.</span></span> <span data-ttu-id="da660-153">Isso cria um problema de ciclo (os dados podem ser lidos em mas os mesmos dados, em seguida, não podem ser gravados).</span><span class="sxs-lookup"><span data-stu-id="da660-153">This creates a round-tripping problem (data can be read in but the same data cannot then be written out).</span></span> <span data-ttu-id="da660-154">Portanto, se `IsRequired` é `true` e `EmitDefaultValue` é `false` em uma versão, a mesma combinação deve ser aplicados a todas as outras versões, de modo que nenhuma versão do contrato de dados poderá produzir um valor que não resultam em uma viagem de ida e.</span><span class="sxs-lookup"><span data-stu-id="da660-154">Therefore, if `IsRequired` is `true` and `EmitDefaultValue` is `false` in one version, the same combination should apply to all other versions such that no version of the data contract would be able to produce a value that does not result in a round trip.</span></span>  
  
## <a name="schema-considerations"></a><span data-ttu-id="da660-155">Considerações de esquema</span><span class="sxs-lookup"><span data-stu-id="da660-155">Schema Considerations</span></span>  
 <span data-ttu-id="da660-156">Para obter uma explicação de como o esquema é produzida para tipos de contrato de dados, consulte [referência de esquema de contrato de dados](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="da660-156">For an explanation of what schema is produced for data contract types, see [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span></span>  
  
 <span data-ttu-id="da660-157">O esquema [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produz para tipos de contrato de dados faz com que não pode fornecer controle de versão.</span><span class="sxs-lookup"><span data-stu-id="da660-157">The schema [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces for data contract types makes no provisions for versioning.</span></span> <span data-ttu-id="da660-158">Ou seja, o esquema exportado de uma determinada versão de um tipo contém somente os membros de dados presentes nessa versão.</span><span class="sxs-lookup"><span data-stu-id="da660-158">That is, the schema exported from a certain version of a type contains only those data members present in that version.</span></span> <span data-ttu-id="da660-159">Implementando o <xref:System.Runtime.Serialization.IExtensibleDataObject> interface não altera o esquema para um tipo.</span><span class="sxs-lookup"><span data-stu-id="da660-159">Implementing the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface does not change the schema for a type.</span></span>  
  
 <span data-ttu-id="da660-160">Membros de dados são exportados para o esquema como elementos opcionais por padrão.</span><span class="sxs-lookup"><span data-stu-id="da660-160">Data members are exported to the schema as optional elements by default.</span></span> <span data-ttu-id="da660-161">Ou seja, o `minOccurs` (atributo XML) valor é definido como 0.</span><span class="sxs-lookup"><span data-stu-id="da660-161">That is, the `minOccurs` (XML attribute) value is set to 0.</span></span> <span data-ttu-id="da660-162">Membros de dados necessários são exportados com `minOccurs` definido como 1.</span><span class="sxs-lookup"><span data-stu-id="da660-162">Required data members are exported with `minOccurs` set to 1.</span></span>  
  
 <span data-ttu-id="da660-163">Muitas das alterações consideradas incondicional, na verdade, são significativas se estrita aderência a esquema é necessária.</span><span class="sxs-lookup"><span data-stu-id="da660-163">Many of the changes considered to be nonbreaking are actually breaking if strict adherence to the schema is required.</span></span> <span data-ttu-id="da660-164">No exemplo anterior, um `CarV1` instância com apenas o `Model` elemento seria validar em relação a `CarV2` esquema (que tem `Model` e `Horsepower`, mas são opcionais).</span><span class="sxs-lookup"><span data-stu-id="da660-164">In the preceding example, a `CarV1` instance with just the `Model` element would validate against the `CarV2` schema (which has both `Model` and `Horsepower`, but both are optional).</span></span> <span data-ttu-id="da660-165">No entanto, o inverso é verdadeiro não: uma `CarV2` instância falhará a validação em relação a `CarV1` esquema.</span><span class="sxs-lookup"><span data-stu-id="da660-165">However, the reverse is not true: a `CarV2` instance would fail validation against the `CarV1` schema.</span></span>  
  
 <span data-ttu-id="da660-166">Ciclo também envolve algumas considerações adicionais.</span><span class="sxs-lookup"><span data-stu-id="da660-166">Round-tripping also entails some additional considerations.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="da660-167">seção "Considerações sobre o esquema" [contratos de dados compatíveis por encaminhamento](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="da660-167"> the "Schema Considerations" section in [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
### <a name="other-permitted-changes"></a><span data-ttu-id="da660-168">Outras alterações de permissão</span><span class="sxs-lookup"><span data-stu-id="da660-168">Other Permitted Changes</span></span>  
 <span data-ttu-id="da660-169">Implementando o <xref:System.Runtime.Serialization.IExtensibleDataObject> interface é uma alteração incondicional.</span><span class="sxs-lookup"><span data-stu-id="da660-169">Implementing the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface is a nonbreaking change.</span></span> <span data-ttu-id="da660-170">No entanto, o suporte do ciclo não existe para versões do tipo antes da versão na qual <xref:System.Runtime.Serialization.IExtensibleDataObject> foi implementado.</span><span class="sxs-lookup"><span data-stu-id="da660-170">However, round-tripping support does not exist for versions of the type prior to the version in which <xref:System.Runtime.Serialization.IExtensibleDataObject> was implemented.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="da660-171">[Contratos de dados compatíveis por encaminhamento](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="da660-171"> [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
## <a name="enumerations"></a><span data-ttu-id="da660-172">Enumerações</span><span class="sxs-lookup"><span data-stu-id="da660-172">Enumerations</span></span>  
 <span data-ttu-id="da660-173">Adicionar ou remover um membro de enumeração é uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="da660-173">Adding or removing an enumeration member is a breaking change.</span></span> <span data-ttu-id="da660-174">Alterando o nome de um membro de enumeração é recentes, a menos que seu nome de contrato é mantido o mesmo que a versão antiga, usando o `EnumMemberAtttribute` atributo.</span><span class="sxs-lookup"><span data-stu-id="da660-174">Changing the name of an enumeration member is breaking, unless its contract name is kept the same as in the old version by using the `EnumMemberAtttribute` attribute.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="da660-175">[Tipos de enumeração em contratos de dados](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="da660-175"> [Enumeration Types in Data Contracts](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="da660-176">Coleções</span><span class="sxs-lookup"><span data-stu-id="da660-176">Collections</span></span>  
 <span data-ttu-id="da660-177">A maioria das alterações de coleção são incondicional porque a maioria dos tipos de coleção são intercambiáveis entre si no modelo de contrato de dados.</span><span class="sxs-lookup"><span data-stu-id="da660-177">Most collection changes are nonbreaking because most collection types are interchangeable with each other in the data contract model.</span></span> <span data-ttu-id="da660-178">No entanto, fazer uma coleção nãopersonalizada personalizada ou vice-versa é uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="da660-178">However, making a noncustomized collection customized or vice versa is a breaking change.</span></span> <span data-ttu-id="da660-179">Além disso, alterar as configurações de personalização da coleção é uma alteração significativa; ou seja, alterar seu nome de contrato de dados e o namespace, nome do elemento, o nome do elemento chave e o nome do elemento de valor de repetição.</span><span class="sxs-lookup"><span data-stu-id="da660-179">Also, changing the collection's customization settings is a breaking change; that is, changing its data contract name and namespace, repeating element name, key element name, and value element name.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="da660-180">personalização da coleção, consulte [tipos de coleção em contratos de dados](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="da660-180"> collection customization, see [Collection Types in Data Contracts](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).</span></span>  
<span data-ttu-id="da660-181">Naturalmente, o contrato de dados de conteúdo de uma coleção (por exemplo, a alteração de uma lista de inteiros para uma lista de cadeias de caracteres) a alteração é uma alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="da660-181">Naturally, changing the data contract of contents of a collection (for example, changing from a list of integers to a list of strings) is a breaking change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da660-182">Consulte também</span><span class="sxs-lookup"><span data-stu-id="da660-182">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>  
 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>  
 <xref:System.Runtime.Serialization.SerializationException>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 [<span data-ttu-id="da660-183">Retornos de chamada de serialização tolerantes à versão</span><span class="sxs-lookup"><span data-stu-id="da660-183">Version-Tolerant Serialization Callbacks</span></span>](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)  
 <span data-ttu-id="da660-184">[Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md) 
(Práticas recomendadas: controle de versão de contrato de dados)</span><span class="sxs-lookup"><span data-stu-id="da660-184">[Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)</span></span>  
 [<span data-ttu-id="da660-185">Usando contratos de dados</span><span class="sxs-lookup"><span data-stu-id="da660-185">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="da660-186">Equivalência de contrato de dados</span><span class="sxs-lookup"><span data-stu-id="da660-186">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="da660-187">Contratos de dados compatíveis por encaminhamento</span><span class="sxs-lookup"><span data-stu-id="da660-187">Forward-Compatible Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)