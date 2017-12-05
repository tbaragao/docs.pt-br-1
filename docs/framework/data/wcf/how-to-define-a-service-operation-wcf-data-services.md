---
title: "Como: definir uma operação de serviço (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dcf4ffd46bbbca0e7e00cad7ae0b2a88f7bd986b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="ba4c6-102">Como: definir uma operação de serviço (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ba4c6-102">How to: Define a Service Operation (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="ba4c6-103">expor os métodos que são definidos no servidor como operações de serviço.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-103"> expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="ba4c6-104">Operações de serviço é permitir que um serviço de dados fornecer acesso por meio de um URI para um método que é definido no servidor.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="ba4c6-105">Para definir uma operação de serviço, se aplicam a [`WebGet]` ou `[WebInvoke]` atributo ao método.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="ba4c6-106">Para dar suporte a operadores de consulta, a operação de serviço deve retornar um <xref:System.Linq.IQueryable%601> instância.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="ba4c6-107">Operações de serviço podem acessar a fonte de dados por meio de <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> propriedade o <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="ba4c6-108">Para obter mais informações, consulte [operações de serviço](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba4c6-108">For more information, see [Service Operations](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ba4c6-109">O exemplo neste tópico define uma operação de serviço chamada `GetOrdersByCity` que retorna um filtrado <xref:System.Linq.IQueryable%601> instância de `Orders` e relacionados `Order_Details` objetos.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="ba4c6-110">O exemplo acessa o <xref:System.Data.Objects.ObjectContext> instância que é a fonte de dados para o serviço de dados de exemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="ba4c6-111">Esse serviço é criado quando você concluir o [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba4c6-111">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="ba4c6-112">Para definir uma operação de serviço no serviço de dados Northwind</span><span class="sxs-lookup"><span data-stu-id="ba4c6-112">To define a service operation in the Northwind data service</span></span>  
  
1.  <span data-ttu-id="ba4c6-113">No projeto do serviço de dados Northwind, abra o arquivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="ba4c6-114">Na classe `Northwind`, defina um método de operação de serviço chamado `GetOrdersByCity` da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ba4c6-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  <span data-ttu-id="ba4c6-115">No `InitializeService` método o `Northwind` de classe, adicione o código a seguir para habilitar o acesso à operação de serviço:</span><span class="sxs-lookup"><span data-stu-id="ba4c6-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="ba4c6-116">A consulta a operação do serviço GetOrdersByCity</span><span class="sxs-lookup"><span data-stu-id="ba4c6-116">To query the GetOrdersByCity service operation</span></span>  
  
-   <span data-ttu-id="ba4c6-117">Em um navegador da Web, digite um dos seguintes URIs para invocar a operação de serviço que é definida no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="ba4c6-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a><span data-ttu-id="ba4c6-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ba4c6-118">Example</span></span>  
 <span data-ttu-id="ba4c6-119">O exemplo a seguir implementa uma operação de serviço chamada `GetOrderByCity` no serviço de dados Northwind.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="ba4c6-120">Essa operação usa o ADO.NET Entity Framework para retornar um conjunto de `Orders` e relacionados `Order_Details` objetos como um <xref:System.Linq.IQueryable%601> instância com base no nome da cidade fornecido.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba4c6-121">Operadores de consulta têm suporte nesse ponto de extremidade de operação de serviço porque o método retorna um <xref:System.Linq.IQueryable%601> instância.</span><span class="sxs-lookup"><span data-stu-id="ba4c6-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a><span data-ttu-id="ba4c6-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ba4c6-122">See Also</span></span>  
 <span data-ttu-id="ba4c6-123">[Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md) (Definindo o WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ba4c6-123">[Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)</span></span>