---
title: ICorDebugValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue
helpviewer_keywords: ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01c94df1d8e6ddef0110268461a2b28f594201b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue-interface1"></a><span data-ttu-id="afd1b-102">ICorDebugValue Interface1</span><span class="sxs-lookup"><span data-stu-id="afd1b-102">ICorDebugValue Interface1</span></span>
<span data-ttu-id="afd1b-103">Reprezentuje wartość w debugowanym procesie.</span><span class="sxs-lookup"><span data-stu-id="afd1b-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="afd1b-104">Wartość może być wartość zapisu lub odczytu.</span><span class="sxs-lookup"><span data-stu-id="afd1b-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afd1b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="afd1b-105">Methods</span></span>  
  
|<span data-ttu-id="afd1b-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="afd1b-106">Method</span></span>|<span data-ttu-id="afd1b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="afd1b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afd1b-108">CreateBreakpoint — metoda</span><span class="sxs-lookup"><span data-stu-id="afd1b-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="afd1b-109">Ta metoda nie jest obecnie zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="afd1b-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="afd1b-110">GetAddress — metoda</span><span class="sxs-lookup"><span data-stu-id="afd1b-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="afd1b-111">Pobiera adres tego `ICorDebugValue` obiektu, który jest w trakcie debugowania.</span><span class="sxs-lookup"><span data-stu-id="afd1b-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="afd1b-112">GetSize — metoda</span><span class="sxs-lookup"><span data-stu-id="afd1b-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="afd1b-113">Pobiera rozmiar w bajtach to `ICorDebugValue` obiektu.</span><span class="sxs-lookup"><span data-stu-id="afd1b-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="afd1b-114">GetType — metoda</span><span class="sxs-lookup"><span data-stu-id="afd1b-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="afd1b-115">Pobiera pierwotny typ `ICorDebugValue` obiektu.</span><span class="sxs-lookup"><span data-stu-id="afd1b-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afd1b-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="afd1b-116">Remarks</span></span>  
 <span data-ttu-id="afd1b-117">Ogólnie rzecz biorąc prawo własności obiektu wartość jest przekazywany, gdy jest zwracany.</span><span class="sxs-lookup"><span data-stu-id="afd1b-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="afd1b-118">Odbiorca jest odpowiedzialny za usuwanie odwołań z obiektu po jego zakończeniu z obiektem.</span><span class="sxs-lookup"><span data-stu-id="afd1b-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="afd1b-119">W zależności od tego, gdzie wartość została pobrana z wartość może pozostają w mocy po wznowieniu procesu.</span><span class="sxs-lookup"><span data-stu-id="afd1b-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="afd1b-120">Tak, ogólnie rzecz biorąc, wartość nie powinna być przechowywana przez wywołanie elementu [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metody.</span><span class="sxs-lookup"><span data-stu-id="afd1b-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afd1b-121">Ten interfejs nie obsługuje wywoływany zdalnie, między komputerami lub między procesami.</span><span class="sxs-lookup"><span data-stu-id="afd1b-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afd1b-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="afd1b-122">Requirements</span></span>  
 <span data-ttu-id="afd1b-123">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afd1b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afd1b-124">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afd1b-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afd1b-125">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afd1b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afd1b-126">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afd1b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afd1b-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="afd1b-127">See Also</span></span>  
    
    
    
    
 [<span data-ttu-id="afd1b-128">ICorDebugValue3 — interfejs</span><span class="sxs-lookup"><span data-stu-id="afd1b-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="afd1b-129">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="afd1b-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)