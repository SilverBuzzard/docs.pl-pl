---
title: Blokowanie wykonywania aplikacji poprzez zakończenie operacji asynchronicznej
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
author: rpetrusha
ms.author: ronpet
dev_langs:
- csharp
- vb
ms.openlocfilehash: 782cb614d74b331cef8ab9f28924104ed15a8a38
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611545"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>Blokowanie wykonywania aplikacji poprzez zakończenie operacji asynchronicznej
Aplikacje, które nie mogą w dalszym ciągu wykonywać inne zadania podczas oczekiwania na wyniki operacji asynchronicznej należy zablokować, aż do zakończenia operacji. Blokowanie wątku głównego aplikacji podczas oczekiwania na zakończenie operacji asynchronicznej, użyj jednej z następujących opcji:  
  
-   Wywoływanie operacji asynchronicznych **zakończenia**_OperationName_ metody. To podejście jest przedstawiona w tym temacie.  
  
-   Użyj <xref:System.IAsyncResult.AsyncWaitHandle%2A> właściwość <xref:System.IAsyncResult> zwrócony przez operację asynchroniczną **rozpocząć *** OperationName* metody. Aby uzyskać przykład demonstrujący takie podejście, zobacz [blokowania aplikacji wykonywania za pomocą właściwości AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Aplikacje, które używają **zakończenia**_OperationName_ zazwyczaj wywoła metodę, aby zablokować do czasu ukończenia operacji asynchronicznej **rozpocząć *** OperationName* metody wykonać wszelkie prace, które może odbywać się bez wyników operacji, a następnie wywołaj **zakończenia**_OperationName_.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu demonstruje, za pomocą metod asynchronicznych we <xref:System.Net.Dns> klasy do pobrania informacji System nazw domen dla komputera określonego przez użytkownika. Należy pamiętać, że `null` (`Nothing` w języku Visual Basic) jest przekazywana <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` i `stateObject` parametry ponieważ tych argumentów nie są wymagane w przypadku korzystania z tej metody.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>Zobacz także

- [Asynchroniczny wzorzec oparty na zdarzeniach (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
- [Asynchroniczny wzorzec oparty na zdarzeniach — omówienie](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
