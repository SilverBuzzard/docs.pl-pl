---
title: "IHostIoCompletionManager::SetMaxThreads — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 084cbf5509583a45f09bcf903e833f4890c5651e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="f4a85-102">IHostIoCompletionManager::SetMaxThreads — Metoda</span><span class="sxs-lookup"><span data-stu-id="f4a85-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="f4a85-103">Ustawia maksymalną liczbę wątków, które spowoduje przyznanie hosta do obsługi żądań We/Wy.</span><span class="sxs-lookup"><span data-stu-id="f4a85-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a85-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f4a85-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4a85-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f4a85-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="f4a85-106">[in] Maksymalna liczba wątków, aby przyznać żądań We/Wy.</span><span class="sxs-lookup"><span data-stu-id="f4a85-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4a85-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f4a85-107">Return Value</span></span>  
  
|<span data-ttu-id="f4a85-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4a85-108">HRESULT</span></span>|<span data-ttu-id="f4a85-109">Opis</span><span class="sxs-lookup"><span data-stu-id="f4a85-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4a85-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4a85-110">S_OK</span></span>|<span data-ttu-id="f4a85-111">`SetMaxThreads`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f4a85-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f4a85-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4a85-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4a85-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="f4a85-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4a85-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4a85-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4a85-115">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="f4a85-115">The call timed out.</span></span>|  
|<span data-ttu-id="f4a85-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4a85-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4a85-117">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="f4a85-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4a85-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4a85-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4a85-119">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="f4a85-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4a85-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4a85-120">E_FAIL</span></span>|<span data-ttu-id="f4a85-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="f4a85-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4a85-122">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="f4a85-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4a85-123">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f4a85-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f4a85-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f4a85-124">E_NOTIMPL</span></span>|<span data-ttu-id="f4a85-125">Host nie zapewniać implementację elementu `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="f4a85-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4a85-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f4a85-126">Remarks</span></span>  
 <span data-ttu-id="f4a85-127">`SetMaxThreads`udostępnia środowisko CLR z okazji, aby ustawić maksymalną liczbę wątków, które są dostępne do obsługi żądań na portów We/Wy.</span><span class="sxs-lookup"><span data-stu-id="f4a85-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="f4a85-128">Host może być konieczne wyłączną kontrolę nad rozmiar puli wątków powodów, takich jak wdrożenia, wydajności i skalowalności.</span><span class="sxs-lookup"><span data-stu-id="f4a85-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="f4a85-129">Z tego powodu hosta nie jest wymagane do zaimplementowania `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="f4a85-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="f4a85-130">W takim przypadku hosta powinien zwrócić E_NOTIMPL z tej metody.</span><span class="sxs-lookup"><span data-stu-id="f4a85-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4a85-131">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f4a85-131">Requirements</span></span>  
 <span data-ttu-id="f4a85-132">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4a85-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a85-133">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4a85-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4a85-134">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4a85-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4a85-135">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a85-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a85-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f4a85-136">See Also</span></span>  
 [<span data-ttu-id="f4a85-137">ICLRIoCompletionManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="f4a85-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="f4a85-138">IHostIoCompletionManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="f4a85-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)