---
title: "_CorValidateImage — Funkcja"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorValidateImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorValidateImage
helpviewer_keywords: _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e2396219a5e4bfd95a9dc7134e2e603ed7a15a3d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="a6d81-102">_CorValidateImage — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a6d81-102">_CorValidateImage Function</span></span>
<span data-ttu-id="a6d81-103">Weryfikuje obrazy moduł zarządzany i powiadamia modułu ładującego systemu operacyjnego po ich załadowaniu.</span><span class="sxs-lookup"><span data-stu-id="a6d81-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6d81-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a6d81-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6d81-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a6d81-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="a6d81-106">[in] Wskaźnik do początkową lokalizację obrazu do sprawdzania poprawności jako kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="a6d81-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="a6d81-107">Obraz musi być już załadowana do pamięci.</span><span class="sxs-lookup"><span data-stu-id="a6d81-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="a6d81-108">[in] Nazwa pliku obrazu.</span><span class="sxs-lookup"><span data-stu-id="a6d81-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6d81-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a6d81-109">Return Value</span></span>  
 <span data-ttu-id="a6d81-110">Ta funkcja zwraca standardowe wartości `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, i `E_FAIL`, a także następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="a6d81-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="a6d81-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a6d81-111">Return value</span></span>|<span data-ttu-id="a6d81-112">Opis</span><span class="sxs-lookup"><span data-stu-id="a6d81-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="a6d81-113">Obraz jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="a6d81-113">The image is invalid.</span></span> <span data-ttu-id="a6d81-114">Ta wartość ma HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="a6d81-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="a6d81-115">Obraz jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="a6d81-115">The image is valid.</span></span> <span data-ttu-id="a6d81-116">Ta wartość ma HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="a6d81-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6d81-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a6d81-117">Remarks</span></span>  
 <span data-ttu-id="a6d81-118">W systemach Windows XP i nowsze wersje modułu ładującego systemu operacyjnego sprawdza, czy modułów zarządzanych, sprawdzając bit katalogu deskryptora COM w typowych nagłówka formatu (COFF) pliku obiektu.</span><span class="sxs-lookup"><span data-stu-id="a6d81-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="a6d81-119">Bit zestaw wskazuje modułu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="a6d81-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="a6d81-120">Jeśli moduł ładujący wykryje moduł zarządzany, załadowanie biblioteki MsCorEE.dll i wywołania `_CorValidateImage`, który wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a6d81-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="a6d81-121">Potwierdza, że obraz jest prawidłowy moduł zarządzany.</span><span class="sxs-lookup"><span data-stu-id="a6d81-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="a6d81-122">Punkt wejścia w obrazie zmienia się na punkt wejścia w środowisku uruchomieniowym języka (wspólnego CLR).</span><span class="sxs-lookup"><span data-stu-id="a6d81-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="a6d81-123">64-bitowe wersje systemu Windows modyfikuje obrazu, który znajduje się w pamięci przez przekształcania z plikiem PE32 plikiem PE32 + format.</span><span class="sxs-lookup"><span data-stu-id="a6d81-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="a6d81-124">Zwraca do modułu ładującego po załadowaniu obrazów modułu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="a6d81-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="a6d81-125">Dla pliku wykonywalnego obrazów, następnie wywołuje modułu ładującego systemu operacyjnego [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funkcji, niezależnie od punkt wejścia określony w pliku wykonywalnym.</span><span class="sxs-lookup"><span data-stu-id="a6d81-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="a6d81-126">Biblioteka DLL zestawu obrazów, wywołuje moduł ładujący [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) funkcji.</span><span class="sxs-lookup"><span data-stu-id="a6d81-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="a6d81-127">`_CorExeMain`lub `_CorDllMain` wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a6d81-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="a6d81-128">Inicjuje środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="a6d81-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="a6d81-129">Lokalizuje zarządzany punkt wejścia w nagłówku CLR zestawu.</span><span class="sxs-lookup"><span data-stu-id="a6d81-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="a6d81-130">Rozpoczyna wykonanie.</span><span class="sxs-lookup"><span data-stu-id="a6d81-130">Begins execution.</span></span>  
  
 <span data-ttu-id="a6d81-131">Wywołania modułu ładującego [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) działać, gdy zarządzany modułu obrazy są usuwane z pamięci.</span><span class="sxs-lookup"><span data-stu-id="a6d81-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="a6d81-132">Jednak ta funkcja nie wykonuje żadnych czynności; Zwraca tylko.</span><span class="sxs-lookup"><span data-stu-id="a6d81-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6d81-133">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a6d81-133">Requirements</span></span>  
 <span data-ttu-id="a6d81-134">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6d81-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6d81-135">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a6d81-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6d81-136">**Biblioteka:** uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6d81-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6d81-137">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6d81-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d81-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a6d81-138">See Also</span></span>  
 [<span data-ttu-id="a6d81-139">Statyczne funkcje globalne metadanych</span><span class="sxs-lookup"><span data-stu-id="a6d81-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)