---
title: ICorProfilerCallback::ObjectsAllocatedByClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78dde5c50666333c02c8c1a9a167e17af3f40341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454354"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass — Metoda
Powiadamia profilera o liczbę wystąpień każdej określonej klasy, które zostały utworzone od czasu ostatniego wyrzucanie elementów bezużytecznych.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a>Parametry  
 `cClassCount`  
 [in] Rozmiar `classIds` i `cObjects` tablic.  
  
 `classIds`  
 [in] Tablica klasy identyfikatorów, w którym każdy identyfikator Określa klasę z co najmniej jedno wystąpienie.  
  
 `cObjects`  
 [in] Tablica liczb całkowitych, gdzie każdy całkowitą określa liczbę wystąpień odpowiedniej klasy w `classIds` tablicy.  
  
## <a name="remarks"></a>Uwagi  
 `classIds` i `cObjects` tablice są tablice równoległych. Na przykład `classIds[i]` i `cObjects[i]` odwołania do tej samej klasy. Jeśli żadne wystąpienie klasy został utworzony od czasu poprzedniego wyrzucanie elementów bezużytecznych, klasa zostanie pominięty. `ObjectsAllocatedByClass` Wywołania zwrotnego nie zgłosi obiekty przydzielone na stercie dużego obiektu.  
  
 Liczby zgłaszanych przez `ObjectsAllocatedByClass` są tylko oszacowania. Dokładne liczniki można użyć [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 `classIds` Tablica może zawierać jeden lub więcej wpisów wartości null, jeśli odpowiednie `cObjects` tablica zawiera typy, które są zwalniane.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICorProfilerCallback, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
