---
title: Funkcja QualifierSet_EndEnumeration (niezarządzany wykaz interfejsów API)
description: Funkcja QualifierSet_EndEnumeration kończy wyliczenia.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbf47dbfddac7d48b78c9d52969de1ef03385c15
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524317"
---
# <a name="qualifiersetendenumeration-function"></a>QualifierSet_EndEnumeration — funkcja
Kończy wyliczenie uruchomione z wywołaniem [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) funkcji.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>Parametry

`vFunc`  
[in] Ten parametr jest nieużywany.

`ptr`   
[in] Wskaźnik do [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) wystąpienia.

## <a name="return-value"></a>Wartość zwracana

Następującą wartość zwrócona przez tę funkcję jest zdefiniowany w *WbemCli.h* pliku nagłówka, lub można zdefiniować ją jako stała w kodzie:

|Stała  |Wartość  |Opis  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | Wywołanie funkcji zakończyło się pomyślnie.  |
  
## <a name="remarks"></a>Uwagi

Ta funkcja zawija wywołanie do [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) metody.

To wywołanie jest zalecane, ale nie jest wymagane. Go natychmiast zwalnia zasoby skojarzone z wyliczenia.

## <a name="requirements"></a>Wymagania  

**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
**Nagłówek:** WMINet_Utils.idl  
  
**Wersje programu .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Zobacz także  
[Usługi WMI i liczniki wydajności (niezarządzany wykaz interfejsów API)](index.md)
