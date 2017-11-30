---
title: Funkcja CertFreeAuthenticodeTimestamperInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeTimestamperInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8b6392e57e641d25d07580fcb6bf630f8d983be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="f6ea1-102">Funkcja CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="f6ea1-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="f6ea1-103">Zwalnia zasoby przydzielone dla [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struktury.</span><span class="sxs-lookup"><span data-stu-id="f6ea1-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ea1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f6ea1-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6ea1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f6ea1-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="f6ea1-106">[w, out] Informacje o stamper czasu do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="f6ea1-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="f6ea1-107">Zobacz [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struktury.</span><span class="sxs-lookup"><span data-stu-id="f6ea1-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6ea1-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f6ea1-108">Return Value</span></span>  
 <span data-ttu-id="f6ea1-109">`S_OK`Jeśli funkcja zakończy się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="f6ea1-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="f6ea1-110">W przeciwnym razie zwraca kod błędu.</span><span class="sxs-lookup"><span data-stu-id="f6ea1-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ea1-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f6ea1-111">See Also</span></span>  
 [<span data-ttu-id="f6ea1-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f6ea1-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)