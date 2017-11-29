---
title: marshalCleanupError MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c78fedaab26ff7f1da7bccd98c83a90e550d9014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="0c92c-102">marshalCleanupError MDA</span><span class="sxs-lookup"><span data-stu-id="0c92c-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="0c92c-103">`marshalCleanupError` Zarządzany Asystent debugowania (MDA) jest aktywowany, gdy środowisko uruchomieniowe języka wspólnego (CLR) napotka błąd podczas próby wyczyścić tymczasowego struktury i pamięć używana na potrzeby organizowanie typów danych między granicami kodu natywnego i zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="0c92c-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0c92c-104">Symptomy</span><span class="sxs-lookup"><span data-stu-id="0c92c-104">Symptoms</span></span>  
 <span data-ttu-id="0c92c-105">Podczas wprowadzania kodu natywnego i zarządzanego przejścia występuje przeciek pamięci, środowiska uruchomieniowego stanu, takich jak kultury wątku nie jest przywracana lub w występują błędy <xref:System.Runtime.InteropServices.SafeHandle> oczyszczania.</span><span class="sxs-lookup"><span data-stu-id="0c92c-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0c92c-106">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="0c92c-106">Cause</span></span>  
 <span data-ttu-id="0c92c-107">Wystąpił nieoczekiwany błąd podczas usuwania tymczasowego struktury.</span><span class="sxs-lookup"><span data-stu-id="0c92c-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0c92c-108">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="0c92c-108">Resolution</span></span>  
 <span data-ttu-id="0c92c-109">Przejrzyj wszystkie <xref:System.Runtime.InteropServices.SafeHandle> destruktor, finalizatora i implementacje organizatora niestandardowego błędów.</span><span class="sxs-lookup"><span data-stu-id="0c92c-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0c92c-110">Wpływ na środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="0c92c-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="0c92c-111">To zdarzenie MDA nie ma wpływu na środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="0c92c-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0c92c-112">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="0c92c-112">Output</span></span>  
 <span data-ttu-id="0c92c-113">Komunikat operacji, które zakończyły się niepowodzeniem podczas oczyszczania funkcji raportowania.</span><span class="sxs-lookup"><span data-stu-id="0c92c-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0c92c-114">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="0c92c-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c92c-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0c92c-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="0c92c-116">Diagnozowanie błędów przy użyciu Asystenci zarządzanego debugowania</span><span class="sxs-lookup"><span data-stu-id="0c92c-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="0c92c-117">Przekazywanie międzyoperacyjne</span><span class="sxs-lookup"><span data-stu-id="0c92c-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)