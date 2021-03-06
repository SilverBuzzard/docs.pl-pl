---
title: -deterministyczne
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: dde79ca9ce6e77102c05fce7c507784457af4a4b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187939"
---
# <a name="-deterministic"></a>-deterministyczne

Powoduje, że kompilator generuje zestawu, którego dane wyjściowe dla bajt jest identyczna w kompilacjach identycznych danych wejściowych. 

## <a name="syntax"></a>Składnia

```
-deterministic
```

## <a name="remarks"></a>Uwagi

Domyślnie dane wyjściowe kompilatora z danego zestawu danych wejściowych jest unikatowa, ponieważ kompilator sam doda sygnaturę czasową i identyfikator GUID, który jest generowany na podstawie liczby losowe. Możesz użyć `-deterministic` opcję, aby wygenerować *deterministyczne zestawu*, jedną z którego zawartość binarna jest identyczne w kompilacji, tak długo, jak dane wejściowe pozostają bez zmian.

Kompilator traktuje następujące dane wejściowe na potrzeby determinizm:

- Sekwencja parametry wiersza polecenia.
- Zawartość pliku odpowiedzi rsp kompilatora.
- Dokładne wersję kompilatora, używane, a jego przywoływanych zestawów.
- Ścieżka bieżącego katalogu.
- Binarny zawartość wszystkich plików jawnie przekazywane do kompilator bezpośrednio lub pośrednio, w tym: 
    - Pliki źródłowe
    - przywoływanych zestawach
    - Moduły odwołania
    - Resources
    - Plik klucza silnej nazwy
    - @ pliki odpowiedzi
    - Analizatory
    - Zestawy reguł
    - Dodatkowe pliki, które mogą być używane przez analizatorów
- Bieżącą kulturą (język, w których dane diagnostyczne i wyjątków są produkowane wiadomości).
- Domyślnym kodowaniem (lub bieżącej stronie kodowej) Jeśli nie określono kodowanie.
- Istnienie, nie istnieje i zawartość plików na ścieżki wyszukiwania kompilatora (określone, na przykład przez `/lib` lub `/recurse`).
- Platforma CLR, na którym jest uruchamiany kompilator.
- Wartość `%LIBPATH%`, co może wpłynąć na ładowanie zależności analizatora.

W przypadku publicznie dostępnego źródła kompilacji deterministycznej może służyć do ustalenia, czy plik binarny jest kompilowany z zaufanego źródła. Również może być przydatne w systemie kompilacji ciągłej do określenia, czy należy wykonać kroki kompilacji, które są zależne od zmian w pliku binarnym. 

## <a name="see-also"></a>Zobacz też
[Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
[Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
