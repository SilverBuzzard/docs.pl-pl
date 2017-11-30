---
title: Metoda ICorDebugDataTarget2::GetImageLocation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d35e35ecf4dfc62575e42a45a861ad685f3f26b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="c982c-102">Metoda ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="c982c-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="c982c-103">Zwraca ścieżkę modułu z adresem podstawowym modułu.</span><span class="sxs-lookup"><span data-stu-id="c982c-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c982c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c982c-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c982c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c982c-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="c982c-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) wartość, która reprezentuje adres podstawowy modułu.</span><span class="sxs-lookup"><span data-stu-id="c982c-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c982c-107">[in] Liczba znaków w buforze, który ma otrzymać ścieżka modułu.</span><span class="sxs-lookup"><span data-stu-id="c982c-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c982c-108">[out] Wskaźnik do liczby znaków zapisane `szName` buforu.</span><span class="sxs-lookup"><span data-stu-id="c982c-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c982c-109">[out] Ścieżka do modułu.</span><span class="sxs-lookup"><span data-stu-id="c982c-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c982c-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c982c-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c982c-111">Ta metoda jest tylko dostępne z platformą .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c982c-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c982c-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c982c-112">Requirements</span></span>  
 <span data-ttu-id="c982c-113">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c982c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c982c-114">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c982c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c982c-115">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c982c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c982c-116">**Wersje programu .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c982c-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c982c-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c982c-117">See Also</span></span>  
 [<span data-ttu-id="c982c-118">Interfejs ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="c982c-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="c982c-119">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="c982c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)