---
title: "Sessões e filas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dffee557bea81c769038729a60b9d270f0f28c6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="sessions-and-queues"></a><span data-ttu-id="8ab98-102">Sessões e filas</span><span class="sxs-lookup"><span data-stu-id="8ab98-102">Sessions and Queues</span></span>
<span data-ttu-id="8ab98-103">Este exemplo demonstra como enviar e receber um conjunto de mensagens relacionadas na comunicação em fila por meio do transporte de enfileiramento de mensagens (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8ab98-103">This sample demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span> <span data-ttu-id="8ab98-104">Este exemplo usa o `netMsmqBinding` associação.</span><span class="sxs-lookup"><span data-stu-id="8ab98-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="8ab98-105">O serviço é um aplicativo de console auto-hospedado para que você possa observar o serviço de recebimento de mensagens na fila.</span><span class="sxs-lookup"><span data-stu-id="8ab98-105">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ab98-106">As instruções de procedimento e a compilação de configuração para este exemplo estão localizadas no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="8ab98-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ab98-107">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="8ab98-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8ab98-108">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8ab98-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8ab98-109">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="8ab98-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8ab98-110">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="8ab98-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 <span data-ttu-id="8ab98-111">Comunicação em fila, o cliente se comunica com o serviço usando uma fila.</span><span class="sxs-lookup"><span data-stu-id="8ab98-111">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="8ab98-112">Mais precisamente, o cliente envia mensagens a uma fila.</span><span class="sxs-lookup"><span data-stu-id="8ab98-112">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="8ab98-113">O serviço recebe mensagens da fila.</span><span class="sxs-lookup"><span data-stu-id="8ab98-113">The service receives messages from the queue.</span></span> <span data-ttu-id="8ab98-114">O serviço e o cliente, portanto, não precisa estar em execução ao mesmo tempo para se comunicar usando uma fila.</span><span class="sxs-lookup"><span data-stu-id="8ab98-114">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="8ab98-115">Às vezes, um cliente envia um conjunto de mensagens que estão relacionados uns aos outros em um grupo.</span><span class="sxs-lookup"><span data-stu-id="8ab98-115">Sometimes, a client sends a set of messages that are related to each other in a group.</span></span> <span data-ttu-id="8ab98-116">Quando as mensagens devem ser processadas juntos ou em uma ordem especificada, uma fila pode ser usada para agrupá-los, para processamento por um único aplicativo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="8ab98-116">When messages must be processed together or in a specified order, a queue can be used to group them together, for processing by a single receiving application.</span></span> <span data-ttu-id="8ab98-117">Isso é particularmente importante quando há vários aplicativos de recebimento em um grupo de servidores e é necessário garantir que um grupo de mensagens é processado pelo mesmo aplicativo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="8ab98-117">This is particularly important when there are several receiving applications on a group of servers and it is necessary to ensure that a group of messages is processed by the same receiving application.</span></span> <span data-ttu-id="8ab98-118">As sessões na fila são um mecanismo usado para enviar e receber um conjunto relacionado de mensagens deve ser processado ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8ab98-118">Queued sessions are a mechanism used to send and receive a related set of messages that must get processed all at once.</span></span> <span data-ttu-id="8ab98-119">Sessões na fila requerem uma transação exibem esse padrão.</span><span class="sxs-lookup"><span data-stu-id="8ab98-119">Queued sessions require a transaction to exhibit this pattern.</span></span>  
  
 <span data-ttu-id="8ab98-120">No exemplo, o cliente envia um número de mensagens para o serviço como parte de uma sessão dentro do escopo de uma única transação.</span><span class="sxs-lookup"><span data-stu-id="8ab98-120">In the sample, the client sends a number of messages to the service as part of a session within the scope of a single transaction.</span></span>  
  
 <span data-ttu-id="8ab98-121">O contrato de serviço é `IOrderTaker`, que define um serviço unidirecional que é adequado para uso com filas.</span><span class="sxs-lookup"><span data-stu-id="8ab98-121">The service contract is `IOrderTaker`, which defines a one-way service that is suitable for use with queues.</span></span> <span data-ttu-id="8ab98-122">O <xref:System.ServiceModel.SessionMode> usado no contrato mostrado no seguinte código de exemplo indica que as mensagens são parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="8ab98-122">The <xref:System.ServiceModel.SessionMode> used in the contract shown in the following sample code indicates that the messages are part of the session.</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface IOrderTaker  
{  
    [OperationContract(IsOneWay = true)]  
    void OpenPurchaseOrder(string customerId);  
  
    [OperationContract(IsOneWay = true)]  
    void AddProductLineItem(string productId, int quantity);  
  
    [OperationContract(IsOneWay = true)]  
    void EndPurchaseOrder();  
}  
```  
  
 <span data-ttu-id="8ab98-123">O serviço define as operações de serviço de forma que a primeira operação inscreve em uma transação, mas não conclui automaticamente a transação.</span><span class="sxs-lookup"><span data-stu-id="8ab98-123">The service defines service operations in such a way that the first operation enlists in a transaction but does not automatically complete the transaction.</span></span> <span data-ttu-id="8ab98-124">Operações subsequentes também se inscrever na mesma transação, mas não concluída automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8ab98-124">Subsequent operations also enlist in the same transaction but do not automatically complete.</span></span> <span data-ttu-id="8ab98-125">A última operação na sessão preenche automaticamente a transação.</span><span class="sxs-lookup"><span data-stu-id="8ab98-125">The last operation in the session automatically completes the transaction.</span></span> <span data-ttu-id="8ab98-126">Portanto, a mesma transação é usada para várias chamadas de operação no contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="8ab98-126">Thus, the same transaction is used for several operation invocations in the service contract.</span></span> <span data-ttu-id="8ab98-127">Se qualquer uma das operações lançar uma exceção, em seguida, a transação será revertida e a sessão é colocada de volta para a fila.</span><span class="sxs-lookup"><span data-stu-id="8ab98-127">If any of the operations throw an exception, then the transaction rolls back and the session is put back into the queue.</span></span> <span data-ttu-id="8ab98-128">Após a conclusão bem-sucedida da última operação, a transação é confirmada.</span><span class="sxs-lookup"><span data-stu-id="8ab98-128">Upon successful completion of the last operation, the transaction is committed.</span></span> <span data-ttu-id="8ab98-129">O serviço usa `PerSession` como o <xref:System.ServiceModel.InstanceContextMode> para receber todas as mensagens em uma sessão na mesma instância do serviço.</span><span class="sxs-lookup"><span data-stu-id="8ab98-129">The service uses `PerSession` as the <xref:System.ServiceModel.InstanceContextMode> to receive all messages in a session on the same instance of the service.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class OrderTakerService : IOrderTaker  
{  
    PurchaseOrder po;  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                 TransactionAutoComplete = false)]  
    public void OpenPurchaseOrder(string customerId)  
    {  
        Console.WriteLine("Creating purchase order");  
        po = new PurchaseOrder(customerId);  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                  TransactionAutoComplete = false)]  
    public void AddProductLineItem(string productId, int quantity)  
    {  
        po.AddProductLineItem(productId, quantity);  
        Console.WriteLine("Product " + productId + " quantity " +   
                            quantity + " added to purchase order");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                  TransactionAutoComplete = true)]  
    public void EndPurchaseOrder()  
    {  
       Console.WriteLine("Purchase Order Completed");  
       Console.WriteLine();  
       Console.WriteLine(po.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="8ab98-130">O serviço é auto-hospedado.</span><span class="sxs-lookup"><span data-stu-id="8ab98-130">The service is self hosted.</span></span> <span data-ttu-id="8ab98-131">Ao usar o transporte MSMQ, a fila usada deve ser criada com antecedência.</span><span class="sxs-lookup"><span data-stu-id="8ab98-131">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="8ab98-132">Isso pode ser feito manualmente ou por meio de código.</span><span class="sxs-lookup"><span data-stu-id="8ab98-132">This can be done manually or through code.</span></span> <span data-ttu-id="8ab98-133">Neste exemplo, o serviço contém <xref:System.Messaging> código para verificar a existência da fila e cria, se necessário.</span><span class="sxs-lookup"><span data-stu-id="8ab98-133">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="8ab98-134">O nome da fila é lido do arquivo de configuração usando o <xref:System.Configuration.ConfigurationManager.AppSettings%2A> classe.</span><span class="sxs-lookup"><span data-stu-id="8ab98-134">The queue name is read from the configuration file using the <xref:System.Configuration.ConfigurationManager.AppSettings%2A> class.</span></span>  
  
```  
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderTakerService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderTakerService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();   
    }  
}  
```  
  
 <span data-ttu-id="8ab98-135">O nome da fila MSMQ é especificado em uma seção appSettings do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="8ab98-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="8ab98-136">O ponto de extremidade para o serviço é definido na seção System. ServiceModel do arquivo de configuração e especifica a `netMsmqBinding` associação.</span><span class="sxs-lookup"><span data-stu-id="8ab98-136">The endpoint for the service is defined in the system.serviceModel section of the configuration file and specifies the `netMsmqBinding` binding.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesSession" />  
</appSettings>  
  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesSession"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
      ...  
    </service>  
  </services>  
  ...  
<system.serviceModel>  
```  
  
 <span data-ttu-id="8ab98-137">O cliente cria um escopo de transação.</span><span class="sxs-lookup"><span data-stu-id="8ab98-137">The client creates a transaction scope.</span></span> <span data-ttu-id="8ab98-138">Todas as mensagens na sessão são enviadas para a fila dentro do escopo da transação, fazendo com que ele será tratado como uma unidade atômica, onde todas as mensagens de êxito ou falha.</span><span class="sxs-lookup"><span data-stu-id="8ab98-138">All messages in the session are sent to the queue within the transaction scope, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="8ab98-139">A transação é confirmada chamando <xref:System.Transactions.TransactionScope.Complete%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ab98-139">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A>.</span></span>  
  
```  
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Create a client with given client endpoint configuration.  
    OrderTakerClient client = new OrderTakerClient("OrderTakerEndpoint");  
    // Open a purchase order.  
    client.OpenPurchaseOrder("somecustomer.com");  
    Console.WriteLine("Purchase Order created");  
  
    // Add product line items.  
    Console.WriteLine("Adding 10 quantities of blue widget");  
    client.AddProductLineItem("Blue Widget", 10);  
  
    Console.WriteLine("Adding 23 quantities of red widget");  
    client.AddProductLineItem("Red Widget", 23);  
  
    // Close the purchase order.  
    Console.WriteLine("Closing the purchase order");  
    client.EndPurchaseOrder();  
  
    //Closing the client gracefully closes the connection and cleans up resources.  
    client.Close();                  
  
    // Complete the transaction.  
    scope.Complete();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="8ab98-140">Você pode usar somente uma única transação para todas as mensagens na sessão e todas as mensagens na sessão devem ser enviadas antes de confirmar a transação.</span><span class="sxs-lookup"><span data-stu-id="8ab98-140">You can use only a single transaction for all messages in the session and all messages in the session must be sent before committing the transaction.</span></span> <span data-ttu-id="8ab98-141">Fechar o cliente fecha a sessão.</span><span class="sxs-lookup"><span data-stu-id="8ab98-141">Closing the client closes the session.</span></span> <span data-ttu-id="8ab98-142">Portanto, o cliente precisa ser fechada antes que a transação seja concluída para enviar todas as mensagens na sessão para a fila.</span><span class="sxs-lookup"><span data-stu-id="8ab98-142">Therefore, the client has to be closed before the transaction is completed to send all messages in the session to the queue.</span></span>  
  
 <span data-ttu-id="8ab98-143">Quando você executar o exemplo, as atividades do cliente e de serviço são exibidas em janelas do console de serviço e o cliente.</span><span class="sxs-lookup"><span data-stu-id="8ab98-143">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="8ab98-144">Você pode ver as mensagens de recebimento de serviço do cliente.</span><span class="sxs-lookup"><span data-stu-id="8ab98-144">You can see the service receive messages from the client.</span></span> <span data-ttu-id="8ab98-145">Pressione ENTER em cada janela de console para desligar o serviço e o cliente.</span><span class="sxs-lookup"><span data-stu-id="8ab98-145">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="8ab98-146">Observe que como enfileiramento de mensagens está em uso, o cliente e o serviço não precisa estar em execução ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8ab98-146">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="8ab98-147">Execute o cliente, desligá-lo e, em seguida, inicie o serviço e ainda receber suas mensagens.</span><span class="sxs-lookup"><span data-stu-id="8ab98-147">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span>  
  
 <span data-ttu-id="8ab98-148">No cliente.</span><span class="sxs-lookup"><span data-stu-id="8ab98-148">On the client.</span></span>  
  
```  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="8ab98-149">O serviço.</span><span class="sxs-lookup"><span data-stu-id="8ab98-149">On the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Creating purchase order  
Product Blue Widget quantity 10 added to purchase order  
Product Red Widget quantity 23 added to purchase order  
Purchase Order Completed  
  
Purchase Order: 7c86fef0-2306-4c51-80e6-bcabcc1a6e5e  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 10 of Blue Widget @unit price: $2985  
                Order LineItem: 23 of Red Widget @unit price: $156  
        Total cost of this order: $33438  
        Order status: Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8ab98-150">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="8ab98-150">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8ab98-151">Certifique-se de que você executou o [único procedimento de instalação para os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8ab98-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8ab98-152">Para criar a edição do c#, C++ ou Visual Basic .NET da solução, siga as instruções em [compilar os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8ab98-152">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8ab98-153">Para executar o exemplo em uma configuração ou entre computadores, siga as instruções em [executando os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8ab98-153">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="8ab98-154">Por padrão, com o <xref:System.ServiceModel.NetMsmqBinding>, segurança de transporte está habilitada.</span><span class="sxs-lookup"><span data-stu-id="8ab98-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="8ab98-155">Há duas propriedades relevantes para a segurança de transporte MSMQ, ou seja, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> e <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` por padrão, o modo de autenticação é definido como `Windows` e o nível de proteção é definido como `Sign`.</span><span class="sxs-lookup"><span data-stu-id="8ab98-155">There are two relevant properties for MSMQ transport security namely, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="8ab98-156">Para o MSMQ fornecer a autenticação e o recurso de assinatura, ele deve ser parte de um domínio e a opção de integração do active directory para o MSMQ deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="8ab98-156">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="8ab98-157">Se você executar esse exemplo em um computador que não atendam a esses critérios, você receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="8ab98-157">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="8ab98-158">Para executar o exemplo em um computador associado a um grupo de trabalho ou sem a integração do active directory</span><span class="sxs-lookup"><span data-stu-id="8ab98-158">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="8ab98-159">Se o computador não faz parte de um domínio ou não tem integração do active directory instalada, desativar a segurança de transporte, definindo o nível de proteção e o modo de autenticação para `None` conforme mostrado no exemplo de configuração.</span><span class="sxs-lookup"><span data-stu-id="8ab98-159">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
                 behaviorConfiguration="OrderTakerServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress=  
             "http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint  
              address=  
            "net.msmq://localhost/private/ServiceModelSamplesSession"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
          <!-- The mex endpoint is exposed at-->      
          <!--http://localhost:8000/ServiceModelSamples/service/mex. -->  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="OrderTakerServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2.  <span data-ttu-id="8ab98-160">Certifique-se de que você altera a configuração no servidor e o cliente antes de executar o exemplo.</span><span class="sxs-lookup"><span data-stu-id="8ab98-160">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ab98-161">Configuração de modo de segurança para `None` é equivalente à configuração <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, e `Message` segurança `None`.</span><span class="sxs-lookup"><span data-stu-id="8ab98-161">Setting security mode to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab98-162">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8ab98-162">See Also</span></span>