---
title: Como executar comandos SQL diretamente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: feffa98fa890856db579553df6624fef1897b173
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="a27dc-102">Como executar comandos SQL diretamente</span><span class="sxs-lookup"><span data-stu-id="a27dc-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="a27dc-103">Presumindo uma conexão de <xref:System.Data.Linq.DataContext>, você pode usar o <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> para executar comandos SQL que não retornam objetos.</span><span class="sxs-lookup"><span data-stu-id="a27dc-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a27dc-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a27dc-104">Example</span></span>  
 <span data-ttu-id="a27dc-105">O exemplo a seguir faz o SQL Server aumentar o UnitPrice em 1,00.</span><span class="sxs-lookup"><span data-stu-id="a27dc-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a27dc-106">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a27dc-106">See Also</span></span>  
 [<span data-ttu-id="a27dc-107">Como: executar diretamente consultas SQL</span><span class="sxs-lookup"><span data-stu-id="a27dc-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [<span data-ttu-id="a27dc-108">Comunicação com o banco de dados</span><span class="sxs-lookup"><span data-stu-id="a27dc-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)