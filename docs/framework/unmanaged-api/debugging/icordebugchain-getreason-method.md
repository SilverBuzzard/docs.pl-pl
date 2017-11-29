---
title: "ICorDebugChain::GetReason — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f0543f31c7b0e5d51f2b12f589ce6dce8552405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="d4f36-102">ICorDebugChain::GetReason — Metoda</span><span class="sxs-lookup"><span data-stu-id="d4f36-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="d4f36-103">Pobiera przyczynę genesis tego wywołania łańcucha.</span><span class="sxs-lookup"><span data-stu-id="d4f36-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f36-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4f36-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4f36-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d4f36-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="d4f36-106">[out] Wskaźnik do wartości cordebugchainreason — wyliczenie wskazujący przyczynę genesis tego wywołania łańcucha (bitowe połączenie).</span><span class="sxs-lookup"><span data-stu-id="d4f36-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f36-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d4f36-107">Requirements</span></span>  
 <span data-ttu-id="d4f36-108">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4f36-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f36-109">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4f36-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4f36-110">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4f36-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4f36-111">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f36-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>