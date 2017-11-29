---
title: "ICLRRuntimeHost::UnloadAppDomain — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.UnloadAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec5e32ccc9311f2f89252c0db5849304f2186de2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="c5dc5-102">ICLRRuntimeHost::UnloadAppDomain — Metoda</span><span class="sxs-lookup"><span data-stu-id="c5dc5-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="c5dc5-103">Zwalnia zarządzanej <xref:System.AppDomain> odpowiadający określony identyfikator numeryczny.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5dc5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c5dc5-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5dc5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c5dc5-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="c5dc5-106">[in] Identyfikator numeryczny wyładować domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="c5dc5-107">[in] `true` aby wskazać, że środowisko uruchomieniowe języka wspólnego (CLR) należy poczekać, aż do zakończenia wykonywania bieżącego wątku aplikacji przed podjęciem próby wyładować domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5dc5-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c5dc5-108">Return Value</span></span>  
  
|<span data-ttu-id="c5dc5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5dc5-109">HRESULT</span></span>|<span data-ttu-id="c5dc5-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c5dc5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5dc5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5dc5-111">S_OK</span></span>|<span data-ttu-id="c5dc5-112">`UnloadAppDomain`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="c5dc5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5dc5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5dc5-114">Środowisko CLR nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5dc5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5dc5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5dc5-116">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-116">The call timed out.</span></span>|  
|<span data-ttu-id="c5dc5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5dc5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5dc5-118">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5dc5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5dc5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5dc5-120">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5dc5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5dc5-121">E_FAIL</span></span>|<span data-ttu-id="c5dc5-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5dc5-123">Jeśli metoda zwraca E_FAIL, CLR nie będzie już można używać w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5dc5-124">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5dc5-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c5dc5-125">Remarks</span></span>  
 <span data-ttu-id="c5dc5-126">Możesz uzyskać identyfikator numeryczny domeny aplikacji wykonuje bieżącego wątku przez wywołanie metody [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="c5dc5-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="c5dc5-127">Ten identyfikator odpowiada <xref:System.AppDomain.Id%2A> właściwości zarządzanej <xref:System.AppDomain> typu.</span><span class="sxs-lookup"><span data-stu-id="c5dc5-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5dc5-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c5dc5-128">Requirements</span></span>  
 <span data-ttu-id="c5dc5-129">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5dc5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5dc5-130">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5dc5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5dc5-131">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5dc5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5dc5-132">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5dc5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5dc5-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c5dc5-133">See Also</span></span>  
 [<span data-ttu-id="c5dc5-134">ICLRRuntimeHost — interfejs</span><span class="sxs-lookup"><span data-stu-id="c5dc5-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)