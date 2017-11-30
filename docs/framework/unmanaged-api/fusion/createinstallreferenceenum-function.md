---
title: "CreateInstallReferenceEnum — Funkcja"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateInstallReference
helpviewer_keywords: CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07c7ec72a66b37798e6e2af523bb024e9dd63d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="9c0b4-102">CreateInstallReferenceEnum — Funkcja</span><span class="sxs-lookup"><span data-stu-id="9c0b4-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="9c0b4-103">Pobiera wskaźnik do [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) wystąpienia, który reprezentuje listę odwołań aplikacji do określonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c0b4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9c0b4-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c0b4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9c0b4-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="9c0b4-106">[out] Zwrócona `IInstallReferenceEnum` wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="9c0b4-107">[in] [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) , które identyfikują zestawu, dla którego wyliczyć odwołań.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9c0b4-108">[in] Flagi wpływające na zachowanie modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="9c0b4-109">[in] Zarezerwowane dla przyszłego rozszerzalności.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9c0b4-110">`pvReserved`musi być odwołanie o wartości null.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c0b4-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9c0b4-111">Requirements</span></span>  
 <span data-ttu-id="9c0b4-112">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c0b4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c0b4-113">**Nagłówek:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9c0b4-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9c0b4-114">**Biblioteka:** Fusion.dll i Mscorwks.dll.a;a;pierwsza.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="9c0b4-115">Użyj Fusion.dll zamiast Mscorwks.dll.a;a;pierwsza, aby upewnić się, że docelowy poprawna wersja programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c0b4-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="9c0b4-116">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c0b4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c0b4-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9c0b4-117">See Also</span></span>  
 [<span data-ttu-id="9c0b4-118">IInstallReferenceEnum — interfejs</span><span class="sxs-lookup"><span data-stu-id="9c0b4-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 [<span data-ttu-id="9c0b4-119">IAssemblyName — interfejs</span><span class="sxs-lookup"><span data-stu-id="9c0b4-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="9c0b4-120">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="9c0b4-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)