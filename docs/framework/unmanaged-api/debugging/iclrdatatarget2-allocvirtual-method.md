---
title: "ICLRDataTarget2::AllocVirtual — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.AllocVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e61b27ae7dcda8cc5e14d9c0f72f74c8bda13169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="f76db-102">ICLRDataTarget2::AllocVirtual — Metoda</span><span class="sxs-lookup"><span data-stu-id="f76db-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="f76db-103">Metoda wywoływana przez wspólnego języka środowiska uruchomieniowego (języka wspólnego CLR) dostępu do usługi danych można przydzielić pamięci w przestrzeni adresowej procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="f76db-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f76db-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f76db-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f76db-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f76db-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="f76db-106">[in] A `CLRDATA_ADDRESS` wartość, która określa żądany adres początkowy pamięci do przydzielenia.</span><span class="sxs-lookup"><span data-stu-id="f76db-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="f76db-107">[in] Rozmiar w bajtach pamięci do przydzielenia.</span><span class="sxs-lookup"><span data-stu-id="f76db-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="f76db-108">[in] Flagi, które kontrolują alokacji pamięci.</span><span class="sxs-lookup"><span data-stu-id="f76db-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="f76db-109">Zobacz Win32 `VirtualAlloc` funkcji.</span><span class="sxs-lookup"><span data-stu-id="f76db-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="f76db-110">[in] Atrybuty ochrony alokacji pamięci.</span><span class="sxs-lookup"><span data-stu-id="f76db-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="f76db-111">Zobacz Win32 `VirtualAlloc` funkcji.</span><span class="sxs-lookup"><span data-stu-id="f76db-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="f76db-112">[out] Wskaźnik do `CLRDATA_ADDRESS` wartość, która określa rzeczywisty adres początkowy alokacji pamięci.</span><span class="sxs-lookup"><span data-stu-id="f76db-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f76db-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f76db-113">Remarks</span></span>  
 <span data-ttu-id="f76db-114">`AllocVirtual` Metody służy jako otoka logiczne dla środowiska Win32 `VirtualAlloc` funkcji.</span><span class="sxs-lookup"><span data-stu-id="f76db-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="f76db-115">Ta metoda jest implementowany przez twórcę debugowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f76db-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f76db-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f76db-116">Requirements</span></span>  
 <span data-ttu-id="f76db-117">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f76db-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f76db-118">**Nagłówek:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f76db-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f76db-119">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f76db-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f76db-120">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f76db-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f76db-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f76db-121">See Also</span></span>  
 [<span data-ttu-id="f76db-122">ICLRDataTarget2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="f76db-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="f76db-123">FreeVirtual — metoda</span><span class="sxs-lookup"><span data-stu-id="f76db-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)