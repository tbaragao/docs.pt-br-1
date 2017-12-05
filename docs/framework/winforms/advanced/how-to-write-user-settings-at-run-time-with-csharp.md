---
title: "Como gravar configurações do usuário em tempo de execução com C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5966aef77c994d2657bd282ad15e8f59a64eeb47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="a4b3c-102">Como gravar configurações do usuário em tempo de execução com C#</span><span class="sxs-lookup"><span data-stu-id="a4b3c-102">How To: Write User Settings at Run Time with C#</span></span> #
<span data-ttu-id="a4b3c-103">As configurações que estão no escopo do aplicativo são somente leitura e só podem ser alteradas em tempo de design ou alterando o arquivo. config entre as sessões do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a4b3c-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="a4b3c-104">Configurações que estão no escopo do usuário, no entanto, podem ser gravadas em tempo de execução assim como qualquer valor de propriedade deve ser alterada.</span><span class="sxs-lookup"><span data-stu-id="a4b3c-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="a4b3c-105">Persiste o novo valor para a duração da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a4b3c-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="a4b3c-106">Você pode manter as alterações das configurações entre sessões do aplicativo chamando o método de salvar.</span><span class="sxs-lookup"><span data-stu-id="a4b3c-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="a4b3c-107">Como: Gravar e salvar as configurações do usuário em tempo de execução com c#</span><span class="sxs-lookup"><span data-stu-id="a4b3c-107">How To: Write and Persist User Settings at Run Time with C#</span></span>  
  
1.  <span data-ttu-id="a4b3c-108">A configuração de acesso e atribuir um novo valor conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="a4b3c-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  <span data-ttu-id="a4b3c-109">Se você quiser manter as alterações das configurações entre sessões do aplicativo, chame o método Save conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="a4b3c-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     <span data-ttu-id="a4b3c-110">Configurações de usuário são salvas em um arquivo em uma subpasta da pasta de dados de aplicativo oculta local do usuário.</span><span class="sxs-lookup"><span data-stu-id="a4b3c-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b3c-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a4b3c-111">See Also</span></span>  
 [<span data-ttu-id="a4b3c-112">Usando configurações do aplicativo e configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="a4b3c-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="a4b3c-113">Como Ler Configurações em Tempo de Execução com C#</span><span class="sxs-lookup"><span data-stu-id="a4b3c-113">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="a4b3c-114">Visão Geral das Configurações do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="a4b3c-114">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)