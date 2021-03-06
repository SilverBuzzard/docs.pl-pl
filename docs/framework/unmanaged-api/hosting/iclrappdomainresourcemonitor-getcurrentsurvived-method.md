---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c179ba23be07e8ff77e1397ed753d4287b22440
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435288"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived — Metoda
Pobiera liczbę bajtów, który udało się przetrwać ostatniego pełnego, blokowanie odzyskiwania pamięci i który odwołuje się bieżącej domeny aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwAppDomainId`  
 [in] Identyfikator domeny żądanej aplikacji.  
  
 `pAppDomainBytesSurvived`  
 [out] Wskaźnik do liczba bajtów, które udało przetrwać po ostatnim wyrzucanie elementów bezużytecznych, które są przechowywane w tej domenie aplikacji. Po pełnej kolekcji ta liczba jest dokładne i kompletne. Po pobraniu tymczasowych ta liczba jest potencjalnie niekompletna. Ten parametr może być `null`.  
  
 `pRuntimeBytesSurvived`  
 [out] Wskaźnik do całkowita liczba bajtów, które udało przetrwać z ostatnich wyrzucanie elementów bezużytecznych. Po pełnej kolekcji liczba ta reprezentuje liczbę bajtów, które są przechowywane w stertach zarządzanych. Po pobraniu tymczasowych liczba ta reprezentuje liczbę bajtów, które są przechowywane na żywo w generacje tymczasowych. Ten parametr może być `null`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|COR_E_APPDOMAINUNLOADED|Domeny aplikacji został zwolniony lub nie istnieje.|  
  
## <a name="remarks"></a>Uwagi  
 Statystyki są aktualizowane tylko po pełnej, blokowanie odzyskiwania pamięci; występuje, oznacza to, kolekcję zawierającą wszystkie generacje i zatrzymuje się podczas pobierania aplikacji. Na przykład <xref:System.GC.Collect?displayProperty=nameWithType> przeciążenie metody wykonuje pełne, blokowanie kolekcji. Współbieżne odzyskiwanie pamięci przebiega w tle i nie są blokowane w aplikacji.  
  
 `GetCurrentSurvived` Metody jest odpowiednikiem niezarządzane zarządzanej <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> właściwości.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MetaHost.h  
  
 **Biblioteka:** uwzględnione jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICLRAppDomainResourceMonitor, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [Monitorowanie zasobów domen aplikacji](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [Hosting, interfejsy](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
