---
title: Stronicowanie (jednostka SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: 7c0a426a80db6eac6b8fdd651a7df7a9d16f577c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148720"
---
# <a name="paging-entity-sql"></a>Stronicowanie (jednostka SQL)
Stronicowanie fizycznych można wykonać przy użyciu [POMIŃ](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) i [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) podklauzul w [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) klauzuli. Do wykonania, fizycznych stronicowania w sposób deterministyczny, należy używać SKIP i LIMIT. Jeśli chcesz ograniczyć liczbę wierszy w wyniku w sposób niejednoznaczny, należy użyć [GÓRNEJ](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md). TOP i SKIP/LIMIT wzajemnie się wykluczają.  
  
## <a name="top-overview"></a>GÓRNY — omówienie  
 Klauzula SELECT może mieć opcjonalny Podklauzula TOP następujące opcjonalny modyfikator właściwy ALL/DISTINCT. Podklauzula TOP Określa, że tylko pierwszy zestaw wierszy zostaną zwrócone w wyniku zapytania. Aby uzyskać więcej informacji, zobacz [GÓRNEJ](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Omówienie limitu i POMIŃ  
 POMIŃ i LIMIT stanowią element klauzuli ORDER BY. Jeśli POMIŃ wyrażenie Podklauzula znajduje się w klauzuli ORDER BY, wyniki będą sortowane według specyfikacji sortowania i zestawu wyników będzie zawierać wiersze, począwszy od następnego wiersza od razu po wyrażeniu SKIP. Na przykład 5 POMIŃ Pomiń pierwsze pięć wierszy i zwraca od szóstego wierszy do przodu. Jeśli LIMIT wyrażenia Podklauzula znajduje się w klauzuli ORDER BY, zapytania będą sortowane według specyfikacji sortowania i wynikowa liczba wierszy, zostanie nałożone przez wyrażenie LIMIT. Na przykład LIMIT 5 ograniczyć zestaw wyników do pięciu wystąpień lub wiersze. POMIŃ i LIMIT nie muszą być używane razem; można użyć tylko POMIŃ lub po prostu OGRANICZYĆ przy użyciu klauzuli ORDER BY. Więcej informacji znajduje się w następujących tematach:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Omówienie jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Jak: Przejrzyj wyniki zapytania](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
