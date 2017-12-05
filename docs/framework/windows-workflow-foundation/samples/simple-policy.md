---
title: Diretiva simples
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a2798c753e1fc526b2f95801d49108a2aba9e8a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="simple-policy"></a><span data-ttu-id="d3fd2-102">Diretiva simples</span><span class="sxs-lookup"><span data-stu-id="d3fd2-102">Simple Policy</span></span>
<span data-ttu-id="d3fd2-103">Este exemplo mostra como usar uma atividade de <xref:System.Workflow.Activities.PolicyActivity> em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="d3fd2-104">O fluxo de trabalho sequencial nesse exemplo é criado usando uma atividade de <xref:System.Workflow.Activities.PolicyActivity> .</span><span class="sxs-lookup"><span data-stu-id="d3fd2-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="d3fd2-105">O fluxo de trabalho define `orderValue`, `customerType`, e os campos de `discount` que são usados para definir um fluxo de trabalho de desconto do produto.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="d3fd2-106">As regras definidas no arquivo das regras definem um valor de desconto que é baseado em `orderValue` e em `customerType`.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="d3fd2-107">`orderValue` e `customerType` são definidos na definição de classe de `SimplePolicyWorkflow` e podem ser modificados para alterar o comportamento.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="d3fd2-108">O desconto resultante é escrito no console no manipulador de eventos <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> que é definido na classe de `SimplePolicyWorkflow` .</span><span class="sxs-lookup"><span data-stu-id="d3fd2-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="d3fd2-109">Para criar o exemplo</span><span class="sxs-lookup"><span data-stu-id="d3fd2-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="d3fd2-110">Abra a solução em [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3fd2-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="d3fd2-111">Crie a solução. CTRL+SHIFT+B pressionando.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d3fd2-112">Executar a solução sem depuração pressionando CTRL + f5.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="d3fd2-113">Para executar a amostra</span><span class="sxs-lookup"><span data-stu-id="d3fd2-113">To run the sample</span></span>  
  
-   <span data-ttu-id="d3fd2-114">Na janela do prompt de comando SDK, execute o arquivo .exe no SimplePolicy \ bin \ debug (ou na pasta \ bin de SimplePolicy para a versão do Visual Basic de exemplo), que está localizado abaixo da pasta principal para o exemplo.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d3fd2-115">Os exemplos podem mais ser instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d3fd2-116">Verificar o seguinte diretório (padrão) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="d3fd2-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d3fd2-117">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="d3fd2-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d3fd2-118">Este exemplo está no seguinte diretório:</span><span class="sxs-lookup"><span data-stu-id="d3fd2-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="d3fd2-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d3fd2-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="d3fd2-120">Diretiva avançada</span><span class="sxs-lookup"><span data-stu-id="d3fd2-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)