---
title: Obsługa częściowych niepowodzeń
description: Architektura Mikrousług .NET konteneryzowanych aplikacji .NET | Obsługa częściowych niepowodzeń
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: 94239fc30292760b2bb28849f8c6ab72c7ceb33d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144731"
---
# <a name="handling-partial-failure"></a>Obsługa częściowych niepowodzeń

W systemach rozproszonych, takich jak aplikacje oparte na mikrousługach istnieje ryzyko wszechobecnym częściowych niepowodzeń. Na przykład jeden mikrousług/kontener może zakończyć się niepowodzeniem lub mogą nie być dostępne odpowiedzi przez krótki czas lub pojedynczej maszyny Wirtualnej lub serwer może ulec awarii. Ponieważ klientów i usług są oddzielne procesy, usługa nie może być przygotowane w sposób terminowy do żądania klienta. Usługa może być przeciążona i działa prawidłowo, bardzo wolno do żądania lub po prostu nie mogą być niedostępne przez krótki czas ze względu na problemy z siecią.

Na przykład należy wziąć pod uwagę strona szczegółów zamówienia, w ramach aplikacji eShopOnContainers przykładowej aplikacji. Jeśli szeregowania mikrousługa odpowiada po użytkownik próbuje przesłać zamówienie, implementacja procesu klienta (aplikacja sieci web MVC) — na przykład, jeśli kod klienta była używana synchroniczne zdalnych wywołań procedury bez limitu czasu — na czas nieokreślony mogłyby spowodować zablokowanie wątków Oczekiwanie na odpowiedź. Oprócz tworzenia płynność pracy, co nie odpowiada oczekiwania zużywa lub blokuje wątek i wątki są bardzo przydatne w aplikacjach o wysokim stopniu skalowalności. W przypadku wielu zablokowane wątki po pewnym czasie poza wątki można uruchomić środowiska uruchomieniowego aplikacji. W takim przypadku aplikacja może stać się globalnie nie odpowiada, a nie tylko częściowo odpowiadać jako show w rysunek 10-1.

![](./media/image1.png)

**Rysunek 10-1**. Błędy częściowe ze względu na zależności, które mają wpływ na dostępność wątku usługi

W przypadku dużej aplikacji opartych na mikrousługach wszelkie częściowych niepowodzeń można uzupełnić informacje, zwłaszcza, jeśli większość interakcji wewnętrznego mikrousług opiera się na synchroniczne wywołania HTTP (co jest uznawane za wzorzec niezalecane). Pomyśl o systemie, który odbiera milionów wywołań przychodzących na dzień. Jeśli system ma nieprawidłowy projekt, który jest oparty na długie łańcuchy synchroniczne wywołania HTTP, tych wywołań przychodzących może spowodować więcej milionów połączenia wychodzące (Załóżmy, że współczynnik 1:4) do dziesiątek, jak wewnętrznych mikrousług jako synchroniczna zależności. Ta sytuacja jest wyświetlany w rysunek 10-2, szczególnie zależności \#3.

![](./media/image2.png)

**Rysunek 10-2**. Wpływ projektu niepoprawne, oferujący funkcje długie łańcuchy żądań HTTP

Sporadyczne niepowodzenia jest gwarantowane w systemie rozproszone i oparte na chmurze, nawet jeśli zależności, co sama ma doskonałej dostępności. Jest fakt, które należy wziąć pod uwagę.

Jeśli nie projektować i implementować techniki, aby zapewnić odporność na uszkodzenia, nawet niewielkie przestoje można większy. Na przykład 50 zależności za pomocą dostępność przez 99,99% dostępności w rezultacie kilka godzin przestojów miesiąc ze względu na to wpływ. Jeśli zależność mikrousług nie powiodło się podczas obsługi dużej liczby żądań, błędów można szybko saturate wszystkie wątki żądania dostępne w poszczególnych usług i awarię całej aplikacji.

![](./media/image3.png)

**Rysunek 10-3**. Częściowe niepowodzenie rozszerzone o mikrousług długie łańcuchy synchroniczne wywołania HTTP

Aby zminimalizować ten problem, w sekcji "*integracji asynchroniczne mikrousług wymusić autonomię w mikrousługach*" (w rozdziale architektury), te wskazówki zachęca się przy użyciu komunikacji asynchronicznej między wewnętrzny mikrousług. 

Ponadto jest istotne, projektowania aplikacji mikrousług i klienta, do obsługi częściowych niepowodzeń — czyli do kompilowania aplikacji mikrousług odporne na błędy i klienta.

>[!div class="step-by-step"]
>[Poprzednie](index.md)
>[dalej](partial-failure-strategies.md)