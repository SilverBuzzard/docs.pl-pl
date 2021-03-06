---
title: IMetaDataEmit::GetSaveSize — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9a65f76aed00e2b848f8603f1fee4d6acc91f99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449160"
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize — Metoda
Pobiera szacowany rozmiar binarne zestaw i jego metadanych w bieżącym zakresie.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fSave`  
 [in] Wartość [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) wyliczenia, która określa, czy można uzyskać dokładne i przybliżony rozmiar. Tylko trzy wartości są prawidłowe: cssAccurate, cssQuick i cssDiscardTransientCAs:  
  
-   cssAccurate Zwraca dokładną Zapisz rozmiar, ale trwa dłużej do obliczenia.  
  
-   cssQuick zwraca rozmiar, uzupełniona na potrzeby bezpieczeństwa, ale zajmuje mniej czasu do obliczenia.  
  
-   Określa, że cssDiscardTransientCAs `GetSaveSize` czy go można wyrzucać discardable atrybutów niestandardowych.  
  
 `pdwSaveSize`  
 [out] Wskaźnik do rozmiaru, który jest wymagany do zapisania pliku.  
  
## <a name="remarks"></a>Uwagi  
 `GetSaveSize` oblicza przestrzeni wymaganej w bajtach, aby zapisać zestawu i wszystkich jego metadanych w bieżącym zakresie. (Wywołanie [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) metody może wyemitować to liczba bajtów.)  
  
 Jeśli element wywołujący implementuje [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfejsu (za pośrednictwem [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) lub [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` będzie wykonywać dwa przebiegi za pośrednictwem metadane do optymalizacji i skompresować je. W przeciwnym razie są wykonywane nie optymalizacji.  
  
 Jeśli będzie przeprowadzana Optymalizacja, Przekaż pierwszy po prostu sortuje struktur metadanych w celu dostrojenia wydajności wyszukiwań w trakcie importu. Ten krok powoduje zwykle przenoszenie rekordy wokół, z efektem ubocznym, że tokeny zachowywane przez narzędzie do użytku w przyszłości są unieważnione. Metadanych nie informuje wywołującego tokenu zmiany dopiero po drugim przebiegu, jednak. W drugim przebiegu różne optymalizacje są wykonywane przeznaczonych do redukowania łącznego rozmiaru metadane, takie jak Optymalizacja zadań (wczesnego wiązania) `mdTypeRef` i `mdMemberRef` tokenów, gdy jest odwołanie do typu lub elementu członkowskiego, który jest zadeklarowana w bieżący zakres metadanych. W tym przebiegu występuje round innego mapowania tokenu. Po tym przebiegu aparat metadanych powiadamia wywołującego, za pośrednictwem jego `IMapToken` interfejsu dowolnego zmienić wartości tokenów.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Cor.h  
  
 **Biblioteka:** używany jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [IMetaDataEmit, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
