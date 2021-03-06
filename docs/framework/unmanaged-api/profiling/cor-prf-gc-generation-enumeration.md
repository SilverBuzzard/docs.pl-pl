---
title: COR_PRF_GC_GENERATION — Wyliczenie
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8283139566050b1858a003316dc46581822a9bbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450157"
---
# <a name="corprfgcgeneration-enumeration"></a>COR_PRF_GC_GENERATION — Wyliczenie
Określa Generowanie wyrzucanie elementów bezużytecznych.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|Obiekt jest przechowywany jako generacji 0.|  
|`COR_PRF_GC_GEN_1`|Obiekt jest przechowywany jako generacji 1.|  
|`COR_PRF_GC_GEN_2`|Obiekt jest przechowywany jako generacji 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Obiekt jest przechowywany w sterty dużego obiektu.|  
  
## <a name="remarks"></a>Uwagi  
 Moduł zbierający elementy bezużyteczne zwiększa wydajność zarządzania pamięcią przez obiekty podziału do generacje oparte na wieku. Moduł zbierający elementy bezużyteczne aktualnie używa trzy generacje numerowane 0, 1, 2, a także segment specjalne stosu, który jest używany dla dużych obiektów. Obiekty, którego rozmiar jest większy niż określonej wartości są przechowywane w sterty dużego obiektu. Inne obiekty przydzielone uruchamiane należących do generacji 0. Wszystkie obiekty znajdujące się po wyrzucania podczas generowania 0 awansowane na pokolenie 1. Przenieś obiekty znajdujące się po wyrzucania podczas generowania 1 do generacji 2.  
  
 Użycie generacje oznacza, że moduł zbierający elementy bezużyteczne ma do pracy z tylko podzestaw przydzielone obiekty w dowolnym momencie.  
  
 `COR_PRF_GC_GENERATION` Wyliczenie jest używany przez [cor_prf_gc_generation_range —](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) struktury.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Profilowanie — wyliczenia](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
