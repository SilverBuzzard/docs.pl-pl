---
title: "ICorProfilerCallback::ModuleAttachedToAssembly — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleAttachedToAssembly
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2c285a42bb48970756a54d5313d2839c76a9835c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="5c980-102">ICorProfilerCallback::ModuleAttachedToAssembly — Metoda</span><span class="sxs-lookup"><span data-stu-id="5c980-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="5c980-103">Powiadamia profilera, czy moduł jest dołączony do zestawu jej nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="5c980-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c980-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5c980-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c980-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5c980-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5c980-106">[in] Identyfikator modułu, który jest dołączony.</span><span class="sxs-lookup"><span data-stu-id="5c980-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="5c980-107">[in] Identyfikator zestawu nadrzędnego, do której jest dołączona modułu.</span><span class="sxs-lookup"><span data-stu-id="5c980-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c980-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5c980-108">Remarks</span></span>  
 <span data-ttu-id="5c980-109">Moduł może zostać załadowany przez tabelę adresów importu (IAT), poprzez wywołanie `LoadLibrary`, lub za pomocą odwołania metadanych.</span><span class="sxs-lookup"><span data-stu-id="5c980-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="5c980-110">W związku z tym wspólne ładujący środowisko uruchomieniowe (języka wspólnego CLR) języka ma wiele ścieżek kodu do określania zestawu, w którym mieszka modułu.</span><span class="sxs-lookup"><span data-stu-id="5c980-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="5c980-111">W związku z tym jest możliwe że po [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) nosi modułu nie może określić, jaki zestaw znajduje się on w i uzyskiwanie Identyfikatora zestawu nadrzędnego nie jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="5c980-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="5c980-112">`ModuleAttachedToAssembly` Metoda jest wywoływana, gdy moduł jest dołączony do zestawu jej nadrzędnej i jej zestaw nadrzędny można uzyskać Identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="5c980-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c980-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5c980-113">Requirements</span></span>  
 <span data-ttu-id="5c980-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c980-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c980-115">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c980-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c980-116">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c980-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c980-117">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c980-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c980-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5c980-118">See Also</span></span>  
 [<span data-ttu-id="5c980-119">ICorProfilerCallback — interfejs</span><span class="sxs-lookup"><span data-stu-id="5c980-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)