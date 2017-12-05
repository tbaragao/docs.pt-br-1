---
title: "Como definir a cadeia de conexão"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 757b70d99a7f2b499d4ad5aab2be2bb61b28af0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="43bb8-102">Como definir a cadeia de conexão</span><span class="sxs-lookup"><span data-stu-id="43bb8-102">How to: Define the Connection String</span></span>
<span data-ttu-id="43bb8-103">Este tópico mostra como definir a cadeia de conexão que é usada ao se conectar a um modelo conceitual.</span><span class="sxs-lookup"><span data-stu-id="43bb8-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="43bb8-104">Este tópico se baseia o [vendas do AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) modelo conceitual.</span><span class="sxs-lookup"><span data-stu-id="43bb8-104">This topic is based on the [AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) conceptual model.</span></span> <span data-ttu-id="43bb8-105">O Modelo de Vendas do AdventureWorks é usado em todos os tópicos relacionados a tarefas na documentação do [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43bb8-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="43bb8-106">Este tópico pressupõe que você já tenha configurado o [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e definir o modelo de vendas do AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="43bb8-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="43bb8-107">Para obter mais informações, consulte [como: definir manualmente os arquivos de modelo e mapeamento](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a).</span><span class="sxs-lookup"><span data-stu-id="43bb8-107">For more information, see [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a).</span></span> <span data-ttu-id="43bb8-108">Os procedimentos neste tópico também estão incluídos no [como: configurar manualmente um projeto do Entity Framework](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).</span><span class="sxs-lookup"><span data-stu-id="43bb8-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43bb8-109">Se você usar o assistente do [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] em um projeto do [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)], ele automaticamente gera um arquivo .edmx e configura o projeto para usar o [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43bb8-109">If you use the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Wizard in a [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="43bb8-110">Para obter mais informações, consulte [como: usar o Assistente de modelo de dados de entidade](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)</span><span class="sxs-lookup"><span data-stu-id="43bb8-110">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)</span></span>  
  
### <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="43bb8-111">Para definir a cadeia de conexão do Entity Framework</span><span class="sxs-lookup"><span data-stu-id="43bb8-111">To define the Entity Framework connection string</span></span>  
  
-   <span data-ttu-id="43bb8-112">Abra o arquivo de configuração do aplicativo de projeto (app.config) e adicione a seguinte cadeia de conexão:</span><span class="sxs-lookup"><span data-stu-id="43bb8-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>  
  
  
  
     <span data-ttu-id="43bb8-113">Se seu projeto não tem um arquivo de configuração do aplicativo, você pode adicionar uma selecionando **Adicionar Novo Item** do **projeto** menu, selecionando o **geral** categoria, selecionando **arquivo de configuração do aplicativo**e, em seguida, clicando em **adicionar**.</span><span class="sxs-lookup"><span data-stu-id="43bb8-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43bb8-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="43bb8-114">See Also</span></span>  
 <span data-ttu-id="43bb8-115">[Quickstart](http://msdn.microsoft.com/en-us/0bc534be-789f-4819-b9f6-76e51d961675) (Início rápido)</span><span class="sxs-lookup"><span data-stu-id="43bb8-115">[Quickstart](http://msdn.microsoft.com/en-us/0bc534be-789f-4819-b9f6-76e51d961675)</span></span>  
 [<span data-ttu-id="43bb8-116">Como: criar um novo arquivo. edmx</span><span class="sxs-lookup"><span data-stu-id="43bb8-116">How to: Create a New .edmx File</span></span>](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)  
 <span data-ttu-id="43bb8-117">[ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) (Ferramentas de modelo de dados de entidade do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="43bb8-117">[ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)</span></span>