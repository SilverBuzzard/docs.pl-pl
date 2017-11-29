---
title: "ICLRErrorReportingManager::GetBucketParametersForCurrentException — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80bf3e9b1cee9f19534f985dccf4508467dbe26e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="980e9-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException — Metoda</span><span class="sxs-lookup"><span data-stu-id="980e9-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="980e9-103">Pobiera bieżący wyjątek w wątku wywołującym pakiet programu Watson.</span><span class="sxs-lookup"><span data-stu-id="980e9-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="980e9-104">A *zasobnik* jest kolekcją błąd danych, który jest powiązany z tym samym wad kodu.</span><span class="sxs-lookup"><span data-stu-id="980e9-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="980e9-105">*Watson* odwołuje się do zestawu technologii do zbierania i analizowania danych, który jest skojarzony z powodu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="980e9-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="980e9-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="980e9-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="980e9-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="980e9-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="980e9-108">[out] Wskaźnik do [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) struktury, która zawiera dane wyjątku błędu.</span><span class="sxs-lookup"><span data-stu-id="980e9-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="980e9-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="980e9-109">Requirements</span></span>  
 <span data-ttu-id="980e9-110">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="980e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="980e9-111">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="980e9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="980e9-112">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="980e9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="980e9-113">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="980e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980e9-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="980e9-114">See Also</span></span>  
 [<span data-ttu-id="980e9-115">ICLRErrorReportingManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="980e9-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)