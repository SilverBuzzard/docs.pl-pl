---
title: "ICorDebugCodeEnum::Next — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCodeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0260f52a32d5cd6d2862927bb0938c90bc430440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="84f3d-102">ICorDebugCodeEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="84f3d-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="84f3d-103">Pobiera określoną liczbę wystąpień "ICorDebugCode" z wyliczenia, zaczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="84f3d-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84f3d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="84f3d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84f3d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="84f3d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="84f3d-106">[in] Liczba `ICorDebugCode` wystąpienia mają zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="84f3d-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="84f3d-107">[out] Tablicy wskaźników, z których każdy wskazuje `ICorDebugCode` obiektu.</span><span class="sxs-lookup"><span data-stu-id="84f3d-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="84f3d-108">[out] Wskaźnik do liczby `ICorDebugCode` wystąpienia faktycznie zwracane.</span><span class="sxs-lookup"><span data-stu-id="84f3d-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="84f3d-109">Ta wartość może mieć wartości zerowej Jeśli `celt` jeden.</span><span class="sxs-lookup"><span data-stu-id="84f3d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84f3d-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="84f3d-110">Requirements</span></span>  
 <span data-ttu-id="84f3d-111">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84f3d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84f3d-112">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84f3d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84f3d-113">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84f3d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84f3d-114">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84f3d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f3d-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="84f3d-115">See Also</span></span>  
    
 