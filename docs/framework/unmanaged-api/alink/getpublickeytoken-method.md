---
title: "GetPublicKeyToken — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetPublicKeyToken
api_location: alink.dll
api_type: COM
f1_keywords: GetPublicKeyToken
helpviewer_keywords: GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f41c8088f095802cf35239afab279d6324adb55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="9a6df-102">GetPublicKeyToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="9a6df-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="9a6df-103">Pobiera token klucza publicznego dla podanego elementu keyfile lub kontener klucza.</span><span class="sxs-lookup"><span data-stu-id="9a6df-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6df-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9a6df-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a6df-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9a6df-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="9a6df-106">Nazwa pliku klucza.</span><span class="sxs-lookup"><span data-stu-id="9a6df-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="9a6df-107">Nazwa kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="9a6df-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="9a6df-108">Adres, gdzie token klucza ma być składowany.</span><span class="sxs-lookup"><span data-stu-id="9a6df-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="9a6df-109">Określa rozmiar w bajtach buforu wskazywanym przez `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="9a6df-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="9a6df-110">Po powrocie zawiera rzeczywista liczba bajtów używanych.</span><span class="sxs-lookup"><span data-stu-id="9a6df-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a6df-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9a6df-111">Return Value</span></span>  
 <span data-ttu-id="9a6df-112">Zwraca wartość S_OK, jeśli metoda zakończy się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="9a6df-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6df-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9a6df-113">Requirements</span></span>  
 <span data-ttu-id="9a6df-114">Wymaga alink.h.</span><span class="sxs-lookup"><span data-stu-id="9a6df-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6df-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a6df-115">See Also</span></span>  
 [<span data-ttu-id="9a6df-116">Ialink2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="9a6df-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9a6df-117">Ialink — interfejs</span><span class="sxs-lookup"><span data-stu-id="9a6df-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9a6df-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="9a6df-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)