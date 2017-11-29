---
title: "IHostGCManager::SuspensionEnding — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9952e62d4979efa0d07b19f183ca71adcc643365
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="10912-102">IHostGCManager::SuspensionEnding — Metoda</span><span class="sxs-lookup"><span data-stu-id="10912-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="10912-103">Powiadamia hosta, że środowisko uruchomieniowe języka wspólnego (CLR) wznawia wykonywanie zadań w wątkach, które została wstrzymana na wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="10912-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10912-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="10912-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10912-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="10912-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="10912-106">[in] Generowanie kolekcji pamięci, która po prostu kończy z którego wątku jest wznawiana.</span><span class="sxs-lookup"><span data-stu-id="10912-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10912-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="10912-107">Return Value</span></span>  
  
|<span data-ttu-id="10912-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10912-108">HRESULT</span></span>|<span data-ttu-id="10912-109">Opis</span><span class="sxs-lookup"><span data-stu-id="10912-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10912-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="10912-110">S_OK</span></span>|<span data-ttu-id="10912-111">`SuspensionEnding`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="10912-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="10912-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10912-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10912-113">Środowisko CLR nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="10912-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10912-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10912-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10912-115">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="10912-115">The call timed out.</span></span>|  
|<span data-ttu-id="10912-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10912-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10912-117">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="10912-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10912-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10912-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10912-119">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="10912-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10912-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10912-120">E_FAIL</span></span>|<span data-ttu-id="10912-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="10912-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10912-122">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="10912-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10912-123">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10912-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10912-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="10912-124">Remarks</span></span>  
 <span data-ttu-id="10912-125">Wywołania CLR `SuspensionEnding` po wykonaniu wyrzucanie elementów bezużytecznych do hosta informuje, że wznawia wykonanie wątku.</span><span class="sxs-lookup"><span data-stu-id="10912-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10912-126">Nie harmonogram wprowadzone wywołanie metody z wątku.</span><span class="sxs-lookup"><span data-stu-id="10912-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10912-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="10912-127">Requirements</span></span>  
 <span data-ttu-id="10912-128">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10912-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10912-129">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10912-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10912-130">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10912-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10912-131">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10912-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10912-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="10912-132">See Also</span></span>  
 [<span data-ttu-id="10912-133">ICLRTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="10912-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="10912-134">ICLRTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="10912-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="10912-135">IHostTask — interfejs</span><span class="sxs-lookup"><span data-stu-id="10912-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="10912-136">IHostTaskManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="10912-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="10912-137">IHostGCManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="10912-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)