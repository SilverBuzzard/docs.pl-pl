---
title: "StackTrace_SimpleContext — Struktura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackTrace_SimpleContext
api_location: diasymreader.dll
api_type: COM
f1_keywords: SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 87ce3d50d6da6a7c23b13fa10123033efbb6c52c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="0d9b9-102">StackTrace_SimpleContext — Struktura</span><span class="sxs-lookup"><span data-stu-id="0d9b9-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="0d9b9-103">Udostępnia prosty kontekstu, którego można użyć zamiast pełnej `CONTEXT` struktury.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d9b9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0d9b9-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="0d9b9-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="0d9b9-105">Members</span></span>  
  
|<span data-ttu-id="0d9b9-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="0d9b9-106">Member</span></span>|<span data-ttu-id="0d9b9-107">Opis</span><span class="sxs-lookup"><span data-stu-id="0d9b9-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="0d9b9-108">Wskaźnik stosu lub wskaźnik stosu enter (ESP) na x86 platform.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="0d9b9-109">Przesunięcie ramki lub rejestru EBP na x86 platform.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="0d9b9-110">Wskaźnik instrukcji lub wprowadź wskaźnika instrukcji (EIP) na x86 platform.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d9b9-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0d9b9-111">Remarks</span></span>  
 <span data-ttu-id="0d9b9-112">Ponieważ funkcji śledzenia stosu zwykle musi zwracać tylko adres, przesunięcie ramki i adres stosu, można opcjonalnie użyć `SimpleContext` struktury zamiast dużej `CONTEXT` struktury.</span><span class="sxs-lookup"><span data-stu-id="0d9b9-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d9b9-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0d9b9-113">Requirements</span></span>  
 <span data-ttu-id="0d9b9-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d9b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d9b9-115">**Nagłówek:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="0d9b9-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="0d9b9-116">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d9b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d9b9-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d9b9-117">See Also</span></span>  
 [<span data-ttu-id="0d9b9-118">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="0d9b9-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="0d9b9-119">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="0d9b9-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)