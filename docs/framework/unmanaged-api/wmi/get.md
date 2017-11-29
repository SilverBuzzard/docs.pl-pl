---
title: "Get — funkcja (niezarządzany wykaz interfejsów API)"
description: "Funkcja Get pobiera wartość określonej właściwości."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Get
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Get
helpviewer_keywords: Get function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75329ee4ee925f4eb74d96d8ce7ef3145eb4a966
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="get-function"></a><span data-ttu-id="4494b-103">Get — funkcja</span><span class="sxs-lookup"><span data-stu-id="4494b-103">Get function</span></span>
<span data-ttu-id="4494b-104">Pobiera wartość określonej właściwości, jeśli istnieje.</span><span class="sxs-lookup"><span data-stu-id="4494b-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4494b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="4494b-105">Syntax</span></span>  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="4494b-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="4494b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4494b-107">[in] Ten parametr nie jest używana.</span><span class="sxs-lookup"><span data-stu-id="4494b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4494b-108">[in] Wskaźnik do [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="4494b-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="4494b-109">[in] Nazwa właściwości.</span><span class="sxs-lookup"><span data-stu-id="4494b-109">[in] The name of the property.</span></span>

<span data-ttu-id="4494b-110">`lFlags`[in] Zastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="4494b-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="4494b-111">Ten parametr musi wynosić 0.</span><span class="sxs-lookup"><span data-stu-id="4494b-111">This parameter must be 0.</span></span>

<span data-ttu-id="4494b-112">`pVal`[out] Jeśli funkcja zwraca pomyślnie, zawiera wartość `wszName` właściwości.</span><span class="sxs-lookup"><span data-stu-id="4494b-112">`pVal` [out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="4494b-113">`pval` Argumentu przypisano poprawny typ i wartość kwalifikatora.</span><span class="sxs-lookup"><span data-stu-id="4494b-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

<span data-ttu-id="4494b-114">`pvtType`[out] Jeśli funkcja zwraca pomyślnie, zawiera [stała typ CIM](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) wskazujące typ właściwości.</span><span class="sxs-lookup"><span data-stu-id="4494b-114">`pvtType` [out] If the function returns successfully, contains a [CIM-type constant](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) that indicates the property type.</span></span> <span data-ttu-id="4494b-115">Można też wartość `null`.</span><span class="sxs-lookup"><span data-stu-id="4494b-115">Its value can also be `null`.</span></span> 

<span data-ttu-id="4494b-116">`plFlavor`[out] Jeśli funkcja zwraca pomyślnie, otrzymuje informacje o źródła właściwości.</span><span class="sxs-lookup"><span data-stu-id="4494b-116">`plFlavor` [out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="4494b-117">Wartość może być `null`, lub jeden z następujących stałych WBEM_FLAVOR_TYPE zdefiniowanych w *WbemCli.h* plik nagłówka:</span><span class="sxs-lookup"><span data-stu-id="4494b-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="4494b-118">Stała</span><span class="sxs-lookup"><span data-stu-id="4494b-118">Constant</span></span>  |<span data-ttu-id="4494b-119">Wartość</span><span class="sxs-lookup"><span data-stu-id="4494b-119">Value</span></span>  |<span data-ttu-id="4494b-120">Opis</span><span class="sxs-lookup"><span data-stu-id="4494b-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="4494b-121">0x40</span><span class="sxs-lookup"><span data-stu-id="4494b-121">0x40</span></span> | <span data-ttu-id="4494b-122">Właściwość jest właściwością standardowy system.</span><span class="sxs-lookup"><span data-stu-id="4494b-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="4494b-123">0x20</span><span class="sxs-lookup"><span data-stu-id="4494b-123">0x20</span></span> | <span data-ttu-id="4494b-124">Dla klasy: właściwość jest dziedziczona z klasy nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="4494b-124">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="4494b-125">Dla wystąpienia obiektu: właściwości, podczas gdy dziedziczone z klasy nadrzędnej, nie został zmodyfikowany przez to wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="4494b-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="4494b-126">0</span><span class="sxs-lookup"><span data-stu-id="4494b-126">0</span></span> | <span data-ttu-id="4494b-127">Dla klasy: właściwość należy do klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="4494b-127">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="4494b-128">Dla wystąpienia obiektu: właściwość jest modyfikowany przez wystąpienie; oznacza to, że podano wartości lub kwalifikator został dodany lub zmodyfikowany.</span><span class="sxs-lookup"><span data-stu-id="4494b-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="4494b-129">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4494b-129">Return value</span></span>

<span data-ttu-id="4494b-130">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *WbemCli.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="4494b-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4494b-131">Stała</span><span class="sxs-lookup"><span data-stu-id="4494b-131">Constant</span></span>  |<span data-ttu-id="4494b-132">Wartość</span><span class="sxs-lookup"><span data-stu-id="4494b-132">Value</span></span>  |<span data-ttu-id="4494b-133">Opis</span><span class="sxs-lookup"><span data-stu-id="4494b-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="4494b-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="4494b-134">0x80041001</span></span> | <span data-ttu-id="4494b-135">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="4494b-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4494b-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4494b-136">0x80041008</span></span> | <span data-ttu-id="4494b-137">Jeden lub więcej parametrów nie są prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="4494b-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="4494b-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4494b-138">0x80041002</span></span> | <span data-ttu-id="4494b-139">Nie znaleziono określonej właściwości.</span><span class="sxs-lookup"><span data-stu-id="4494b-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4494b-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4494b-140">0x80041006</span></span> | <span data-ttu-id="4494b-141">Za mało pamięci jest dostępna do wykonania operacji.</span><span class="sxs-lookup"><span data-stu-id="4494b-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4494b-142">0</span><span class="sxs-lookup"><span data-stu-id="4494b-142">0</span></span> | <span data-ttu-id="4494b-143">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="4494b-143">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4494b-144">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4494b-144">Remarks</span></span>

<span data-ttu-id="4494b-145">Ta funkcja jest zawijana wywołanie [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="4494b-145">This function wraps a call to the [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="4494b-146">`Get` Funkcji można również zwrócić właściwości systemu.</span><span class="sxs-lookup"><span data-stu-id="4494b-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="4494b-147">`pVal` Argumentu przypisano poprawny typ i wartość kwalifikator i COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) — funkcja</span><span class="sxs-lookup"><span data-stu-id="4494b-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) function</span></span>

## <a name="requirements"></a><span data-ttu-id="4494b-148">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4494b-148">Requirements</span></span>  
 <span data-ttu-id="4494b-149">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4494b-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4494b-150">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4494b-150">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4494b-151">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4494b-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4494b-152">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4494b-152">See also</span></span>  
[<span data-ttu-id="4494b-153">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="4494b-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)