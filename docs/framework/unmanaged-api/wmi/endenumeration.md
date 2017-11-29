---
title: "Funkcja EndEnumeration (niezarządzany wykaz interfejsów API)"
description: "Funkcja EndEnumeration kończy wyliczenia."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: EndEnumeration
helpviewer_keywords: EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 043fce26870e5af2850b9f2e91e7e97c7bee6c90
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="endenumeration-function"></a><span data-ttu-id="e4cc2-103">Funkcja EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="e4cc2-103">EndEnumeration function</span></span>
<span data-ttu-id="e4cc2-104">Kończy sekwencji wyliczenie wprowadzenie wywołanie [funkcja Beingenumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="e4cc2-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e4cc2-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="e4cc2-105">Syntax</span></span>  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="e4cc2-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="e4cc2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e4cc2-107">[in] Ten parametr nie jest używana.</span><span class="sxs-lookup"><span data-stu-id="e4cc2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e4cc2-108">[in] Wskaźnik do [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="e4cc2-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>


## <a name="return-value"></a><span data-ttu-id="e4cc2-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e4cc2-109">Return value</span></span>

<span data-ttu-id="e4cc2-110">Następujące wartości zwracane przez tę funkcję są zdefiniowane w *WbemCli.h* pliku nagłówka, lub należy je zdefiniować jako stałe w kodzie:</span><span class="sxs-lookup"><span data-stu-id="e4cc2-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e4cc2-111">Stała</span><span class="sxs-lookup"><span data-stu-id="e4cc2-111">Constant</span></span>  |<span data-ttu-id="e4cc2-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="e4cc2-112">Value</span></span>  |<span data-ttu-id="e4cc2-113">Opis</span><span class="sxs-lookup"><span data-stu-id="e4cc2-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e4cc2-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e4cc2-114">0x80041001</span></span> | <span data-ttu-id="e4cc2-115">Wystąpił błąd ogólny.</span><span class="sxs-lookup"><span data-stu-id="e4cc2-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e4cc2-116">0</span><span class="sxs-lookup"><span data-stu-id="e4cc2-116">0</span></span> | <span data-ttu-id="e4cc2-117">Wywołanie funkcji zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e4cc2-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e4cc2-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e4cc2-118">Remarks</span></span>

<span data-ttu-id="e4cc2-119">Ta funkcja jest zawijana wywołanie [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) metody.</span><span class="sxs-lookup"><span data-stu-id="e4cc2-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="e4cc2-120">Wywołanie `EndEnumeration` funkcja nie jest wymagana, ale jest zalecane, ponieważ zwalnia zasoby skojarzone z wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="e4cc2-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="e4cc2-121">Jednak resoruces są alokację automatycznie po uruchomieniu dalej wyliczenie lub obiektu jest zwalniany.</span><span class="sxs-lookup"><span data-stu-id="e4cc2-121">However, the resoruces are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4cc2-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e4cc2-122">Requirements</span></span>  
 <span data-ttu-id="e4cc2-123">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4cc2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4cc2-124">**Nagłówek:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e4cc2-124">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e4cc2-125">**Wersje programu .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e4cc2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cc2-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e4cc2-126">See also</span></span>  
[<span data-ttu-id="e4cc2-127">Liczniki wydajności (niezarządzany wykaz interfejsów API) i usługi WMI</span><span class="sxs-lookup"><span data-stu-id="e4cc2-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)