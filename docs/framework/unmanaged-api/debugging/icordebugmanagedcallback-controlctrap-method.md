---
title: "ICorDebugManagedCallback::ControlCTrap — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ControlCTrap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df6aab0f8f220e53c8aab0d40a8b300d95822068
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="2f67e-102">ICorDebugManagedCallback::ControlCTrap — Metoda</span><span class="sxs-lookup"><span data-stu-id="2f67e-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="2f67e-103">Powiadamia debugera, że w procesie, który jest debugowany jest kolor CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="2f67e-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f67e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2f67e-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f67e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2f67e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="2f67e-106">[in] Wskaźnik do obiektu ICorDebugProcess, który reprezentuje proces, w którym jest kolor CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="2f67e-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f67e-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2f67e-107">Return Value</span></span>  
  
|<span data-ttu-id="2f67e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f67e-108">HRESULT</span></span>|<span data-ttu-id="2f67e-109">Opis</span><span class="sxs-lookup"><span data-stu-id="2f67e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f67e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f67e-110">S_OK</span></span>|<span data-ttu-id="2f67e-111">Debuger będzie obsługiwać pułapki klawisze CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="2f67e-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="2f67e-112">WARTOŚCI S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2f67e-112">S_FALSE</span></span>|<span data-ttu-id="2f67e-113">Debuger nie będzie obsługiwać pułapki klawisze CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="2f67e-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f67e-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2f67e-114">Remarks</span></span>  
 <span data-ttu-id="2f67e-115">Wszystkich domen aplikacji w ramach procesu zostały zatrzymane dla tego wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="2f67e-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f67e-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2f67e-116">Requirements</span></span>  
 <span data-ttu-id="2f67e-117">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f67e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f67e-118">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f67e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f67e-119">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f67e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f67e-120">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f67e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f67e-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2f67e-121">See Also</span></span>  
 [<span data-ttu-id="2f67e-122">ICorDebugManagedCallback — interfejs</span><span class="sxs-lookup"><span data-stu-id="2f67e-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)