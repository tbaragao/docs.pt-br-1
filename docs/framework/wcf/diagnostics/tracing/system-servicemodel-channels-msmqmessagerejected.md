---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 87d6e6fc3205fff9bd977ebe77004dfa489098cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681216"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ rejeitadas a mensagem.  
  
## <a name="description"></a>Descrição  
 Este rastreamento indica que uma mensagem MSMQ foi rejeitada.  
  
 Mensagens do MSMQ podem ser rejeitadas quando o Windows Communication Foundation (WCF) (usado com o NetMsmqBinding ou MsmqIntegrationBinding) não pode processá-los. Essas mensagens são denominadas mensagens suspeitas. Uma mensagem suspeita é rejeitada quando o `ReceiveErrorHandling` sobre o NetMsmqBinding ou MsmqIntegrationBinding estiver definida como `Reject`. Uma mensagem rejeitada é entregue para o remetente [fila de inatividade](https://go.microsoft.com/fwlink/?LinkID=99544).  
  
 Ver [tratamento de mensagens suspeitas](https://go.microsoft.com/fwlink/?LinkID=99546) para obter mais detalhes sobre quando as mensagens se tornarão suspeitas e como configurar seu serviço para tratá-las adequadamente.  
  
 Ver [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) para obter mais detalhes sobre o que significa que uma mensagem rejeitada no MSMQ.  
  
## <a name="see-also"></a>Consulte também
- [Rastreamento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Usando o rastreamento para solucionar problemas do seu aplicativo](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnósticos](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Manipulação de mensagens suspeitas](https://go.microsoft.com/fwlink/?LinkID=99546)
- [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548)
