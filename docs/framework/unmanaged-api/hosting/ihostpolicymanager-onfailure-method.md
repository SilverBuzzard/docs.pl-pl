---
title: "IHostPolicyManager::OnFailure — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd8c5e071eca6b287b570006f33d7a1a43c1def9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="b79ce-102">IHostPolicyManager::OnFailure — Metoda</span><span class="sxs-lookup"><span data-stu-id="b79ce-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="b79ce-103">Powiadamia hosta, którego środowisko uruchomieniowe języka wspólnego (CLR) ma mieć z akcją określoną przez wywołanie do [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metody w odpowiedzi na błąd alokacji lub odzyskiwanie zasobu.</span><span class="sxs-lookup"><span data-stu-id="b79ce-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b79ce-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b79ce-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b79ce-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b79ce-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="b79ce-106">[in] Jeden z [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) wartości i wskazujący rodzaj awarii, któremu odpowiada środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="b79ce-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="b79ce-107">[in] Jeden z [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) wartości i wskazujący akcję CLR trwa w odpowiedzi na `failure`.</span><span class="sxs-lookup"><span data-stu-id="b79ce-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b79ce-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b79ce-108">Return Value</span></span>  
  
|<span data-ttu-id="b79ce-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b79ce-109">HRESULT</span></span>|<span data-ttu-id="b79ce-110">Opis</span><span class="sxs-lookup"><span data-stu-id="b79ce-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b79ce-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b79ce-111">S_OK</span></span>|<span data-ttu-id="b79ce-112">`OnFailure`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b79ce-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="b79ce-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b79ce-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b79ce-114">Środowisko CLR nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="b79ce-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b79ce-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b79ce-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b79ce-116">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="b79ce-116">The call timed out.</span></span>|  
|<span data-ttu-id="b79ce-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b79ce-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b79ce-118">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="b79ce-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b79ce-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b79ce-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b79ce-120">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="b79ce-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b79ce-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b79ce-121">E_FAIL</span></span>|<span data-ttu-id="b79ce-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="b79ce-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b79ce-123">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="b79ce-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b79ce-124">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b79ce-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b79ce-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b79ce-125">Requirements</span></span>  
 <span data-ttu-id="b79ce-126">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b79ce-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b79ce-127">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b79ce-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b79ce-128">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b79ce-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b79ce-129">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b79ce-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79ce-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b79ce-130">See Also</span></span>  
 [<span data-ttu-id="b79ce-131">EClrFailure — wyliczenie</span><span class="sxs-lookup"><span data-stu-id="b79ce-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="b79ce-132">EPolicyAction — wyliczenie</span><span class="sxs-lookup"><span data-stu-id="b79ce-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="b79ce-133">ICLRPolicyManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="b79ce-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="b79ce-134">IHostPolicyManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="b79ce-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)