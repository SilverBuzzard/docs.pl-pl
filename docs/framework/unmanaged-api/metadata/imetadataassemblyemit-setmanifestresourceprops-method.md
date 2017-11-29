---
title: "IMetaDataAssemblyEmit::SetManifestResourceProps — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetManifestResourceProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3cc447b18ac6ccabd642ab0a1fb5b887fb4fbe4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="0b6f7-102">IMetaDataAssemblyEmit::SetManifestResourceProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="0b6f7-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="0b6f7-103">Modyfikuje określony `ManifestResource` struktura metadanych.</span><span class="sxs-lookup"><span data-stu-id="0b6f7-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6f7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0b6f7-104">Syntax</span></span>  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b6f7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0b6f7-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="0b6f7-106">[in] Token, który określa `ManifestResource` struktura metadanych ma być zmodyfikowana.</span><span class="sxs-lookup"><span data-stu-id="0b6f7-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="0b6f7-107">[in] Token typu `File` lub `AssemblyRef`, która jest mapowana do dostawcy zasobów.</span><span class="sxs-lookup"><span data-stu-id="0b6f7-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="0b6f7-108">[in] Przesunięcie początku zasobów w pliku.</span><span class="sxs-lookup"><span data-stu-id="0b6f7-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="0b6f7-109">[in] Bitowe połączenie wartości flagi, które określają atrybuty zasobu.</span><span class="sxs-lookup"><span data-stu-id="0b6f7-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b6f7-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0b6f7-110">Remarks</span></span>  
 <span data-ttu-id="0b6f7-111">Aby utworzyć `ManifestResource` metadanych struktury, użyj [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) metody.</span><span class="sxs-lookup"><span data-stu-id="0b6f7-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b6f7-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0b6f7-112">Requirements</span></span>  
 <span data-ttu-id="0b6f7-113">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b6f7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b6f7-114">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0b6f7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b6f7-115">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b6f7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b6f7-116">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b6f7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6f7-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0b6f7-117">See Also</span></span>  
 [<span data-ttu-id="0b6f7-118">IMetaDataAssemblyEmit — interfejs</span><span class="sxs-lookup"><span data-stu-id="0b6f7-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)