---
title: "ICorProfilerFunctionEnum — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum
helpviewer_keywords: ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1067fa6738b23492b3a58500b4cb6ba1d030304f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="ed4db-102">ICorProfilerFunctionEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ed4db-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="ed4db-103">Udostępnia metody sekwencyjnie iterowania po kolekcji funkcji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="ed4db-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed4db-104">Metody</span><span class="sxs-lookup"><span data-stu-id="ed4db-104">Methods</span></span>  
  
|<span data-ttu-id="ed4db-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="ed4db-105">Method</span></span>|<span data-ttu-id="ed4db-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ed4db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed4db-107">Clone — metoda</span><span class="sxs-lookup"><span data-stu-id="ed4db-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="ed4db-108">Pobiera wskaźnika interfejsu kopię `ICorProfilerFunctionEnum` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="ed4db-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="ed4db-109">GetCount — metoda</span><span class="sxs-lookup"><span data-stu-id="ed4db-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="ed4db-110">Pobiera liczbę funkcji, które zostały załadowane do aplikacji lub Wymuś załadowanych przez profiler.</span><span class="sxs-lookup"><span data-stu-id="ed4db-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="ed4db-111">Next — metoda</span><span class="sxs-lookup"><span data-stu-id="ed4db-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="ed4db-112">Pobiera określoną liczbę funkcji ciągłego z sekwencyjną kolekcją funkcji, zaczynając od modułu wyliczającego bieżącej pozycji w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="ed4db-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="ed4db-113">Reset — metoda</span><span class="sxs-lookup"><span data-stu-id="ed4db-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="ed4db-114">Przesuwa kursor modułu wyliczającego pozycji początkowej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="ed4db-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="ed4db-115">SKIP — metoda</span><span class="sxs-lookup"><span data-stu-id="ed4db-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="ed4db-116">Przesuwa kursor modułu wyliczającego z jego bieżącym położeniu tak, aby określoną liczbę elementów są pomijane.</span><span class="sxs-lookup"><span data-stu-id="ed4db-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed4db-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ed4db-117">Remarks</span></span>  
 <span data-ttu-id="ed4db-118">`ICorProfilerFunctionEnum` Interfejs jest moduł wyliczający.</span><span class="sxs-lookup"><span data-stu-id="ed4db-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="ed4db-119">Umożliwia odbiorcy tablicy do ściągania elementów od nadawcy szybkością, który jest odpowiedni dla odbiornika.</span><span class="sxs-lookup"><span data-stu-id="ed4db-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="ed4db-120">Innymi słowy odbiorca jest w stanie jawnie sterowanie przepływem elementów tablicy, zapobiegając problemów związanych z przekazywanie dużych tablic jako parametrów metody.</span><span class="sxs-lookup"><span data-stu-id="ed4db-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="ed4db-121">`ICorProfilerFunctionEnum`Wylicza za pośrednictwem funkcji, które zostały już kompilacji JIT, ale nie zawiera funkcje, które są ładowane z obrazów macierzystych wygenerowane z Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="ed4db-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed4db-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ed4db-122">Requirements</span></span>  
 <span data-ttu-id="ed4db-123">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed4db-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed4db-124">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed4db-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed4db-125">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed4db-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed4db-126">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed4db-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4db-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ed4db-127">See Also</span></span>  
 [<span data-ttu-id="ed4db-128">ICorProfilerInfo — interfejs</span><span class="sxs-lookup"><span data-stu-id="ed4db-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="ed4db-129">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="ed4db-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="ed4db-130">EnumJITedFunctions — metoda</span><span class="sxs-lookup"><span data-stu-id="ed4db-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)