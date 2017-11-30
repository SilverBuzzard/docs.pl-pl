---
title: "IMetaDataDispenserEx::SetOption — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.SetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a58ac4379522c13125f98df058cd67bceb7cdbd1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexsetoption-method"></a><span data-ttu-id="36288-102">IMetaDataDispenserEx::SetOption — Metoda</span><span class="sxs-lookup"><span data-stu-id="36288-102">IMetaDataDispenserEx::SetOption Method</span></span>
<span data-ttu-id="36288-103">Ustawia określoną opcję do podanej wartości w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="36288-103">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="36288-104">Opcję określa sposób obsługi wywołania do bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="36288-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36288-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="36288-105">Syntax</span></span>  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36288-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="36288-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="36288-107">[in] Wskaźnik identyfikator GUID, który określa opcje do ustawienia.</span><span class="sxs-lookup"><span data-stu-id="36288-107">[in] A pointer to a GUID that specifies the option to be set.</span></span>  
  
 `pValue`  
 <span data-ttu-id="36288-108">[in] Wartość do użycia, aby ustawić opcję.</span><span class="sxs-lookup"><span data-stu-id="36288-108">[in] The value to use to set the option.</span></span> <span data-ttu-id="36288-109">Typ tej wartości musi być określona opcja typu Wariant.</span><span class="sxs-lookup"><span data-stu-id="36288-109">The type of this value must be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36288-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="36288-110">Remarks</span></span>  
 <span data-ttu-id="36288-111">W poniższej tabeli wymieniono dostępne identyfikatory GUID który `optionId` może wskazywać parametru i prawidłowe wartości odpowiednich dla `pValue` parametru.</span><span class="sxs-lookup"><span data-stu-id="36288-111">The following table lists the available GUIDs that the `optionId` parameter can point to and the corresponding valid values for the `pValue` parameter.</span></span>  
  
|<span data-ttu-id="36288-112">Identyfikator GUID</span><span class="sxs-lookup"><span data-stu-id="36288-112">GUID</span></span>|<span data-ttu-id="36288-113">Opis</span><span class="sxs-lookup"><span data-stu-id="36288-113">Description</span></span>|<span data-ttu-id="36288-114">`pValue`Parametr</span><span class="sxs-lookup"><span data-stu-id="36288-114">`pValue` Parameter</span></span>|  
|----------|-----------------|------------------------|  
|<span data-ttu-id="36288-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="36288-115">MetaDataCheckDuplicatesFor</span></span>|<span data-ttu-id="36288-116">Określa elementy, które są sprawdzane pod kątem duplikatów.</span><span class="sxs-lookup"><span data-stu-id="36288-116">Controls which items are checked for duplicates.</span></span> <span data-ttu-id="36288-117">Zawsze należy wywołać [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) metodę, która tworzy nowy element, możesz poprosić metodę, aby sprawdzić, czy element już istnieje w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="36288-117">Each time you call an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) method that creates a new item, you can ask the method to check whether the item already exists in the current scope.</span></span> <span data-ttu-id="36288-118">Na przykład można sprawdzić obecność `mdMethodDef` elementy; w takim przypadku, gdy jest wywoływana [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), sprawdzi, czy metoda nie istnieje już w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="36288-118">For example, you can check for the existence of `mdMethodDef` items; in this case, when you call [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), it will check that the method does not already exist in the current scope.</span></span> <span data-ttu-id="36288-119">To sprawdzenie korzysta z klucza, który unikatowo identyfikuje danej metody: nadrzędnego typu, nazwy i podpisu.</span><span class="sxs-lookup"><span data-stu-id="36288-119">This check uses the key that uniquely identifies a given method: parent type, name, and signature.</span></span>|<span data-ttu-id="36288-120">Musi być typ variant typu UI4 i musi zawierać kombinację wartości [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-120">Must be a variant of type UI4, and must contain a combination of the values of the [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="36288-121">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="36288-121">MetaDataRefToDefCheck</span></span>|<span data-ttu-id="36288-122">Formanty, które odwołuje się do elementów są konwertowane na definicje.</span><span class="sxs-lookup"><span data-stu-id="36288-122">Controls which referenced items are converted to definitions.</span></span> <span data-ttu-id="36288-123">Domyślnie aparat metadanych będzie optymalizacji kodu za pomocą konwersji elementu z odwołaniem do jego definicji, jeśli przywoływany element faktycznie jest zdefiniowana w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="36288-123">By default, the metadata engine will optimize the code by converting a referenced item to its definition if the referenced item is actually defined in the current scope.</span></span>|<span data-ttu-id="36288-124">Musi być typ variant typu UI4 i musi zawierać kombinację wartości [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-124">Must be a variant of type UI4, and must contain a combination of the values of the [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="36288-125">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="36288-125">MetaDataNotificationForTokenMovement</span></span>|<span data-ttu-id="36288-126">Formanty ponownie token, który mapuje występujących podczas scalania metadanych Generowanie wywołań zwrotnych.</span><span class="sxs-lookup"><span data-stu-id="36288-126">Controls which token remaps occurring during a metadata merge generate callbacks.</span></span> <span data-ttu-id="36288-127">Użyj [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) metodę ustanawiania Twojej [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfejsu.</span><span class="sxs-lookup"><span data-stu-id="36288-127">Use the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method to establish your [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface.</span></span>|<span data-ttu-id="36288-128">Musi być typ variant typu UI4 i musi zawierać kombinację wartości [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-128">Must be a variant of type UI4, and must contain a combination of the values of the [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="36288-129">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="36288-129">MetaDataSetENC</span></span>|<span data-ttu-id="36288-130">Steruje zachowaniem edit-and-continue (ENC).</span><span class="sxs-lookup"><span data-stu-id="36288-130">Controls the behavior of edit-and-continue (ENC).</span></span> <span data-ttu-id="36288-131">Można ustawić tylko jeden tryb zachowania w czasie.</span><span class="sxs-lookup"><span data-stu-id="36288-131">Only one mode of behavior can be set at a time.</span></span>|<span data-ttu-id="36288-132">Musi być typ variant typu UI4 i musi zawierać wartość [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-132">Must be a variant of type UI4, and must contain a value of the [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) enumeration.</span></span> <span data-ttu-id="36288-133">Wartość nie jest maską bitów.</span><span class="sxs-lookup"><span data-stu-id="36288-133">The value is not a bitmask.</span></span>|  
|<span data-ttu-id="36288-134">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="36288-134">MetaDataErrorIfEmitOutOfOrder</span></span>|<span data-ttu-id="36288-135">Formanty, które błędy emitowany poza kolejnością Generowanie wywołań zwrotnych.</span><span class="sxs-lookup"><span data-stu-id="36288-135">Controls which emitted-out-of-order errors generate callbacks.</span></span> <span data-ttu-id="36288-136">Emitowanie poza kolejnością metadanych nie jest krytyczny; Jednak jeśli Emituj metadanych w kolejności, która jest ich drużyna jest faworytem przez aparat metadanych, metadanych jest mniejszych i w związku z tym można efektywniej przeszukiwać.</span><span class="sxs-lookup"><span data-stu-id="36288-136">Emitting metadata out of order is not fatal; however, if you emit metadata in an order that is favored by the metadata engine, the metadata is more compact and therefore can be more efficiently searched.</span></span> <span data-ttu-id="36288-137">Użyj `IMetaDataEmit::SetHandler` metodę ustanawiania Twojej [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) interfejsu.</span><span class="sxs-lookup"><span data-stu-id="36288-137">Use the `IMetaDataEmit::SetHandler` method to establish your [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) interface.</span></span>|<span data-ttu-id="36288-138">Musi być typ variant typu UI4 i musi zawierać kombinację wartości [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-138">Must be a variant of type UI4, and must contain a combination of the values of the [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="36288-139">MetaDataImportOption</span><span class="sxs-lookup"><span data-stu-id="36288-139">MetaDataImportOption</span></span>|<span data-ttu-id="36288-140">Określa, jakie rodzaje elementów, które zostały usunięte podczas ENC są pobierane przez moduł wyliczający.</span><span class="sxs-lookup"><span data-stu-id="36288-140">Controls which kinds of items that were deleted during an ENC are retrieved by an enumerator.</span></span>|<span data-ttu-id="36288-141">Musi być typ variant typu UI4 i musi zawierać kombinację wartości [CorImportOptions — wyliczenie](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-141">Must be a variant of type UI4, and must contain a combination of the values of the [CorImportOptions Enumeration](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="36288-142">MetaDataThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="36288-142">MetaDataThreadSafetyOptions</span></span>|<span data-ttu-id="36288-143">Określa, czy aparat metadanych uzyskuje odczytywania/zapisywania blokad, zapewniając bezpieczeństwo wątków.</span><span class="sxs-lookup"><span data-stu-id="36288-143">Controls whether the metadata engine obtains reader/writer locks, thereby ensuring thread safety.</span></span> <span data-ttu-id="36288-144">Domyślnie aparat zakłada, że dostęp jednowątkowe przez obiekt wywołujący, więc nie blokuje są uzyskiwane.</span><span class="sxs-lookup"><span data-stu-id="36288-144">By default, the engine assumes that access is single-threaded by the caller, so no locks are obtained.</span></span> <span data-ttu-id="36288-145">Klienci są zobowiązani do utrzymywania synchronizacji odpowiednich wątku przy użyciu metadanych interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="36288-145">Clients are responsible for maintaining proper thread synchronization when using the metadata API.</span></span>|<span data-ttu-id="36288-146">Musi być typ variant typu UI4 i musi zawierać wartość [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-146">Must be a variant of type UI4, and must contain a value of the [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enumeration.</span></span> <span data-ttu-id="36288-147">Wartość nie jest maską bitów.</span><span class="sxs-lookup"><span data-stu-id="36288-147">The value is not a bitmask.</span></span>|  
|<span data-ttu-id="36288-148">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="36288-148">MetaDataGenerateTCEAdapters</span></span>|<span data-ttu-id="36288-149">Określa, czy importer biblioteki typów powinien wygenerować kart silnie sprzężonego zdarzenia (tce programu) dla kontenerów punktu połączenia COM.</span><span class="sxs-lookup"><span data-stu-id="36288-149">Controls whether the type library importer should generate the tightly coupled event (TCE) adapters for COM connection point containers.</span></span>|<span data-ttu-id="36288-150">Musi być typ variant typu wartość logiczna.</span><span class="sxs-lookup"><span data-stu-id="36288-150">Must be a variant of type BOOL.</span></span> <span data-ttu-id="36288-151">Jeśli `pValue` ma ustawioną wartość `true`, kart tce programu generuje importer biblioteki typów.</span><span class="sxs-lookup"><span data-stu-id="36288-151">If `pValue` is set to `true`, the type library importer generates the TCE adapters.</span></span>|  
|<span data-ttu-id="36288-152">MetaDataTypeLibImportNamespace</span><span class="sxs-lookup"><span data-stu-id="36288-152">MetaDataTypeLibImportNamespace</span></span>|<span data-ttu-id="36288-153">Określa przestrzeń nazw z systemem innym niż domyślny dla biblioteki typów, który jest importowany.</span><span class="sxs-lookup"><span data-stu-id="36288-153">Specifies a non-default namespace for the type library that is being imported.</span></span>|<span data-ttu-id="36288-154">Musi być wartością null lub wariant typu BSTR.</span><span class="sxs-lookup"><span data-stu-id="36288-154">Must be either a null value or a variant of type BSTR.</span></span> <span data-ttu-id="36288-155">Jeśli `pValue` jest wartością null bieżącej przestrzeni nazw jest ustawiona na wartość null; w przeciwnym razie, bieżącej przestrzeni nazw jest ustawiona na ciąg, który jest przechowywany w typ BSTR variant.</span><span class="sxs-lookup"><span data-stu-id="36288-155">If `pValue` is a null value, the current namespace is set to null; otherwise, the current namespace is set to the string that is held in the variant's BSTR type.</span></span>|  
|<span data-ttu-id="36288-156">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="36288-156">MetaDataLinkerOptions</span></span>|<span data-ttu-id="36288-157">Określa, czy konsolidator powinien wygenerować zestawu lub pliku modułu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="36288-157">Controls whether the linker should generate an assembly or a .NET Framework module file.</span></span>|<span data-ttu-id="36288-158">Musi być typ variant typu UI4 i musi zawierać kombinację wartości [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-158">Must be a variant of type UI4, and must contain a combination of the values of the [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="36288-159">MetaDataRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="36288-159">MetaDataRuntimeVersion</span></span>|<span data-ttu-id="36288-160">Określa wersję środowiska CLR, względem którego został skompilowany ten obraz.</span><span class="sxs-lookup"><span data-stu-id="36288-160">Specifies the version of the common language runtime against which this image was built.</span></span> <span data-ttu-id="36288-161">Wersja jest przechowywana jako ciąg znaków, takich jak "v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="36288-161">The version is stored as a string, such as "v1.0.3705".</span></span>|<span data-ttu-id="36288-162">Musi to być wartość null, wartość VT_EMPTY lub wariant typu BSTR.</span><span class="sxs-lookup"><span data-stu-id="36288-162">Must be a null value, a VT_EMPTY value, or a variant of type BSTR.</span></span> <span data-ttu-id="36288-163">Jeśli `pValue` jest wersja środowiska uruchomieniowego null, jest ustawiony na wartość null.</span><span class="sxs-lookup"><span data-stu-id="36288-163">If `pValue` is null, the runtime version is set to null.</span></span> <span data-ttu-id="36288-164">Jeśli `pValue` jest VT_EMPTY, wersja jest ustawiana wartość domyślna, która jest przenoszony z wersji Mscorwks.dll.a;a;pierwsza, w którym wykonywany jest kod metadanych.</span><span class="sxs-lookup"><span data-stu-id="36288-164">If `pValue` is VT_EMPTY, the version is set to a default value, which is drawn from the version of Mscorwks.dll within which the metadata code is running.</span></span> <span data-ttu-id="36288-165">W przeciwnym razie wersja środowiska uruchomieniowego jest ustawiona na ciąg, który jest przechowywany w typ BSTR variant.</span><span class="sxs-lookup"><span data-stu-id="36288-165">Otherwise, the runtime version is set to the string that is held in the variant's BSTR type.</span></span>|  
|<span data-ttu-id="36288-166">MetaDataMergerOptions</span><span class="sxs-lookup"><span data-stu-id="36288-166">MetaDataMergerOptions</span></span>|<span data-ttu-id="36288-167">Określa opcje scalania metadanych.</span><span class="sxs-lookup"><span data-stu-id="36288-167">Specifies options for merging metadata.</span></span>|<span data-ttu-id="36288-168">Musi być typ variant typu UI4 i musi zawierać kombinację wartości `MergeFlags` wyliczenia, który jest opisany w pliku CorHdr.h.</span><span class="sxs-lookup"><span data-stu-id="36288-168">Must be a variant of type UI4, and must contain a combination of the values of the `MergeFlags` enumeration, which is described in the CorHdr.h file.</span></span>|  
|<span data-ttu-id="36288-169">MetaDataPreserveLocalRefs</span><span class="sxs-lookup"><span data-stu-id="36288-169">MetaDataPreserveLocalRefs</span></span>|<span data-ttu-id="36288-170">Wyłącza optymalizacji lokalnego odwołania do definicji.</span><span class="sxs-lookup"><span data-stu-id="36288-170">Disables optimizing local references into definitions.</span></span>|<span data-ttu-id="36288-171">Musi zawierać kombinację wartości [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="36288-171">Must contain a combination of the values of the [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36288-172">Wymagania</span><span class="sxs-lookup"><span data-stu-id="36288-172">Requirements</span></span>  
 <span data-ttu-id="36288-173">**Platforma:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36288-173">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36288-174">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36288-174">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36288-175">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36288-175">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36288-176">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36288-176">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36288-177">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="36288-177">See Also</span></span>  
 [<span data-ttu-id="36288-178">IMetaDataDispenserEx — interfejs</span><span class="sxs-lookup"><span data-stu-id="36288-178">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="36288-179">IMetaDataDispenser — interfejs</span><span class="sxs-lookup"><span data-stu-id="36288-179">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)