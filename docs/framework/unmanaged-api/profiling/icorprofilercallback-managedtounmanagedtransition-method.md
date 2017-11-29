---
title: "ICorProfilerCallback::ManagedToUnmanagedTransition — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ManagedToUnmanagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9da8dd44d5b87cd1c65b8b8837c9dd378039d332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="305aa-102">ICorProfilerCallback::ManagedToUnmanagedTransition — Metoda</span><span class="sxs-lookup"><span data-stu-id="305aa-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="305aa-103">Powiadamia profilera, że nastąpiło przejście z kodu zarządzanego do kodu niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="305aa-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="305aa-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="305aa-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="305aa-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="305aa-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="305aa-106">[in] Identyfikator funkcji, która jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="305aa-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="305aa-107">[in] Wartość [cor_prf_transition_reason —](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) wyliczenia, która wskazuje, czy przejście wystąpiły z powodu wywołania do kodu niezarządzanego z kodu zarządzanego lub ze względu na powrót z funkcją zarządzaną wywoływane przez jeden z niezarządzanych.</span><span class="sxs-lookup"><span data-stu-id="305aa-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="305aa-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="305aa-108">Remarks</span></span>  
 <span data-ttu-id="305aa-109">Jeśli wartość `reason` jest COR_PRF_TRANSITION_CALL, funkcja identyfikator jest, że niezarządzanych funkcji, która będzie nigdy nie zostały skompilowane przy użyciu kompilatora just in time.</span><span class="sxs-lookup"><span data-stu-id="305aa-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="305aa-110">Funkcje niezarządzane mają podstawowe informacje skojarzone z nimi, takie jak nazwa i niektóre metadane.</span><span class="sxs-lookup"><span data-stu-id="305aa-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="305aa-111">Jeśli niezarządzanej funkcji została wywołana przy użyciu platformy niejawne wywołania (PInvoke), środowisko uruchomieniowe nie może określić docelowy wywołania i wartość `functionId` będzie mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="305aa-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="305aa-112">Aby uzyskać więcej informacji na niejawna funkcja PInvoke, zobacz [za pomocą międzyoperacyjności języka C++ (niejawna funkcja PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="305aa-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="305aa-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="305aa-113">Requirements</span></span>  
 <span data-ttu-id="305aa-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="305aa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="305aa-115">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="305aa-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="305aa-116">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="305aa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="305aa-117">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="305aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305aa-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="305aa-118">See Also</span></span>  
 [<span data-ttu-id="305aa-119">ICorProfilerCallback — interfejs</span><span class="sxs-lookup"><span data-stu-id="305aa-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="305aa-120">UnmanagedToManagedTransition — metoda</span><span class="sxs-lookup"><span data-stu-id="305aa-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [<span data-ttu-id="305aa-121">Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)</span><span class="sxs-lookup"><span data-stu-id="305aa-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)