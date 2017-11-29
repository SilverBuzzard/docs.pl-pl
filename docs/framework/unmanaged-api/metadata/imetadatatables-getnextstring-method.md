---
title: "IMetaDataTables::GetNextString — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9d9062ef164c5a50652ed78786725967fda999d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="d767b-102">IMetaDataTables::GetNextString — Metoda</span><span class="sxs-lookup"><span data-stu-id="d767b-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="d767b-103">Pobiera indeks następnego ciągu w bieżącej kolumny tabeli.</span><span class="sxs-lookup"><span data-stu-id="d767b-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d767b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d767b-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d767b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d767b-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="d767b-106">[in] Wartość indeksu z kolumną tabeli ciąg.</span><span class="sxs-lookup"><span data-stu-id="d767b-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="d767b-107">[out] Wskaźnik do indeksu ciągu dalej w tej kolumnie.</span><span class="sxs-lookup"><span data-stu-id="d767b-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d767b-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d767b-108">Requirements</span></span>  
 <span data-ttu-id="d767b-109">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d767b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d767b-110">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d767b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d767b-111">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d767b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d767b-112">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d767b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d767b-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d767b-113">See Also</span></span>  
 [<span data-ttu-id="d767b-114">IMetaDataTables — interfejs</span><span class="sxs-lookup"><span data-stu-id="d767b-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="d767b-115">IMetaDataTables2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="d767b-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)