---
title: Metody typu System.String
ms.date: 03/30/2017
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
ms.openlocfilehash: a6a8ce897cc6ac15f3452d2ba98b1b12bee544c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360073"
---
# <a name="systemstring-methods"></a>Metody typu System.String
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nie obsługuje następujących <xref:System.String> metody.  
  
## <a name="unsupported-systemstring-methods-in-general"></a>Ogólnie rzecz biorąc nieobsługiwany metod typu System.String  
 Nieobsługiwany <xref:System.String> metody ogólne:  
  
-   Overloads pamiętać kultury (metody, które przyjmują `CultureInfo`  /  `StringComparison`  /  `IFormatProvider`).  
  
-   Metody zająć lub utworzyć `char` tablicy.  
  
## <a name="unsupported-systemstring-static-methods"></a>Metody nieobsługiwanego typu System.String statyczne  
  
|Metody nieobsługiwanego typu System.String statyczne|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a>Nieobsługiwany System.String metod niestatycznych  
  
|Nieobsługiwany System.String metod niestatycznych|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a>Różnice z platformy .NET  
  
-   Sortowania programu SQL Server, które mogą obowiązywać na serwerze, a zatem będą dostarczać porównania z uwzględnieniem kultury, bez uwzględniania wielkości liter domyślnie nie uwzględniają zapytania. To zachowanie różni się od domyślnej, z uwzględnieniem wielkości liter semantyki .NET Framework.  
  
-   Gdy `LastIndexOf` jest zwraca wartość 0, ciągiem `NULL` lub znaleziono pozycji wynosi 0.  
  
-   Nieoczekiwane wyniki mogą być zwracane z łączenia lub inne operacje na ciągach o stałej długości (`CHAR`, `NCHAR`), ponieważ te typy mają automatycznie dopełnienie stosowane w bazie danych.  
  
-   Ponieważ wiele metod, takich jak `Replace`, `ToLower`, `ToUpper`i indeksatora znak, ma nie prawidłowy Translacja `TEXT` lub `NTEXT` kolumn i XML, `SqlExceptions` wystąpić, jeśli translacji normalnie. To zachowanie jest uważany za akceptowalne dla tych typów. Jednak wszystkie operacje na ciągach musi być zgodna wspólnego języka środowiska uruchomieniowego (języka wspólnego CLR) semantykę dla `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, i `NVARCHAR(max)`.  
  
## <a name="see-also"></a>Zobacz też  
 [Typy danych i funkcje](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
