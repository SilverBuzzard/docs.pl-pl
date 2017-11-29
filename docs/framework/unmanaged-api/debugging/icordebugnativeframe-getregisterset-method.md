---
title: "ICorDebugNativeFrame::GetRegisterSet — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7689632d41971d85417501e9a7f90712a07b34bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="8c340-102">ICorDebugNativeFrame::GetRegisterSet — Metoda</span><span class="sxs-lookup"><span data-stu-id="8c340-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="8c340-103">Pobiera rejestr, ustaw dla tej ramki stosu.</span><span class="sxs-lookup"><span data-stu-id="8c340-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c340-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8c340-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c340-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8c340-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="8c340-106">[out] Wskaźnik do adresu [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) obiekt, który reprezentuje rejestru ustawić dla tej ramki stosu.</span><span class="sxs-lookup"><span data-stu-id="8c340-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c340-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8c340-107">Requirements</span></span>  
 <span data-ttu-id="8c340-108">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c340-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c340-109">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c340-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c340-110">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c340-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c340-111">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c340-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c340-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8c340-112">See Also</span></span>  
 