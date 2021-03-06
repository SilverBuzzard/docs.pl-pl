---
title: Class — Instrukcja (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: 1d81ce148e237df6997934f70c294630f6cc7b8d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235885"
---
# <a name="class-statement-visual-basic"></a>Class — Instrukcja (Visual Basic)
Deklaruje nazwę klasy i wprowadza definicje zmiennych, właściwości, zdarzeń i procedur, które obejmuje ta klasa.  
  
## <a name="syntax"></a>Składnia  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>Części  
  
|Termin|Definicja|  
|---|---|  
|`attributelist`|Opcjonalna. Zobacz temat [Lista atrybutów](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcjonalna. Może to być jeden z następujących elementów:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Private protected](../../language-reference/modifiers/private-protected.md)<br/><br/> Zobacz temat [Poziomy dostępu w języku Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcjonalna. Zobacz [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Opcjonalna. Zobacz [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Opcjonalna. Zobacz [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Opcjonalna. Wskazuje częściową definicję klasy. Zobacz [Partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Wymagana. Nazwa tej klasy. Zobacz temat[Zadeklarowane nazwy elementów](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcjonalna. Określa, że to klasy ogólnej.|  
|`typelist`|Wymagane w przypadku użycia [z](../../../visual-basic/language-reference/statements/of-clause.md) — słowo kluczowe. Lista parametrów typu dla tej klasy. Zobacz [Lista typów](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcjonalna. Wskazuje, że ta klasa dziedziczy członków innej klasy. Zobacz [Inherits — instrukcja](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Wymagane w przypadku użycia instrukcji `Inherits`. Nazwa klasy, z której pochodzi ta klasa.|  
|`Implements`|Opcjonalna. Wskazuje, że ta klasa implementuje elementy członkowskie jednego lub więcej interfejsów. Zobacz [Implements, instrukcja](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Wymagane w przypadku użycia instrukcji `Implements`. Nazwy interfejsów, który implementuje ta klasa.|  
|`statements`|Opcjonalna. Instrukcje, które definiują elementy członkowskie tej klasy.|  
|`End Class`|Wymagana. Kończy definicję `Class`.|  
  
## <a name="remarks"></a>Uwagi  
 Instrukcja `Class` definiuje nowy typ danych. *Klasa* jest podstawowym blokiem konstrukcyjnym w programowaniu obiektowym. Aby uzyskać więcej informacji, zobacz temat [Obiekty i klasy](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 Instrukcji `Class` można użyć tylko na poziomie przestrzeni nazw lub modułu. Oznacza to, że *kontekstem deklaracji* klasy musi być plik źródłowy, przestrzeń nazw, klasa, struktura, moduł lub interfejs, a nie może nim być procedura ani blok. Aby uzyskać więcej informacji, zobacz [Kontekst deklaracji i domyślne poziomy dostępu](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Każde wystąpienie klasy ma okres istnienia niezależny od innych wystąpień. Okres ten rozpoczyna się, gdy klasa jest tworzona przez klauzulę z [operatorem New](../../../visual-basic/language-reference/operators/new-operator.md) lub funkcję taką jak <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Okres istnienia kończy się, gdy wszystkie zmienne wskazujące na wystąpienie zostaną ustawione na [Nothing](../../../visual-basic/language-reference/nothing.md) lub wystąpienia innych klas.  
  
 Klasy domyślnie [Friend](../../../visual-basic/language-reference/modifiers/friend.md) dostępu. Poziomy dostępu można zmienić za pomocą modyfikatorów dostępu. Aby uzyskać więcej informacji, zobacz temat [Poziomy dostępu w języku Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>reguły  
  
-   **Zagnieżdżanie.** Jedną klasę można zdefiniować w obrębie innej. Klasa zewnętrzna to *klasa zawierająca*, a klasa wewnętrzna — *klasa zagnieżdżona*.  
  
-   **Dziedziczenie.** Jeśli klasa używa [instrukcji Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), można określić tylko jedną klasę podstawową lub interfejs. Klasa nie może dziedziczyć z więcej niż jednego elementu.  
  
     Klasa nie może dziedziczyć z innej klasy o bardziej restrykcyjnym poziomie dostępu. Na przykład klasa `Public` nie może dziedziczyć z klasy `Friend`.  
  
     Klasa nie może też dziedziczyć z klasy w niej zagnieżdżonej.  
  
-   **Implementacja.** Jeśli klasa używa [instrukcji Implements](../../../visual-basic/language-reference/statements/implements-statement.md), musisz zaimplementować każdy element członkowski zdefiniowany przez każdy interfejs określony w `interfacenames`. Wyjątkiem jest ponowna implementacja elementu członkowskiego klasy podstawowej. Aby uzyskać więcej informacji, zobacz sekcję „Ponowna implementacja” w artykule [Klauzula Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Właściwość domyślna.** Klasa może określać maksymalnie jedną właściwość jako swoją *właściwość domyślną*. Aby uzyskać więcej informacji, zobacz temat [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Zachowanie  
  
-   **Poziom dostępu.** W obrębie klasy można zadeklarować każdy element członkowski z własnym poziomem dostępu. Domyślnie elementy członkowskie klasy mają poziom dostępu [Public](../../../visual-basic/language-reference/modifiers/public.md), z wyjątkiem zmiennych i stałych, których poziom domyślny to [Private](../../../visual-basic/language-reference/modifiers/private.md). Gdy klasa ma poziom dostępu bardziej restrykcyjny niż jeden z jej elementów członkowskich, pierwszeństwo ma poziom dostępu klasy.  
  
-   **Zakres.** Zakresem klasy jest cała zawierająca ją przestrzeń nazw, klasa, struktura lub moduł.  
  
     Zakresem każdego elementu członkowskiego klasy jest cała klasa.  
  
     **Okres istnienia.** Visual Basic nie obsługuje klas statycznych. Funkcjonalność odpowiadająca klasie statycznej jest realizowana przez moduł. Aby uzyskać więcej informacji, zobacz artykuł [Instrukcja Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Elementy członkowskie klasy mają swoje okresy istnienia zależne od tego, jak i gdzie są zadeklarowane. Aby uzyskać więcej informacji, zobacz [Okres istnienia w Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Kwalifikacja.** Kod poza klasą musi określać nazwę elementu członkowskiego z nazwą tej klasy.  
  
     Jeśli kod wewnątrz klasy zagnieżdżonej wykonuje niekwalifikowane odwołanie do elementu programistycznego, Visual Basic wyszukuje ten element najpierw w klasie zagnieżdżonej, a następnie w klasie zawierającej — i tak dalej aż do najbardziej zewnętrznego elementu zawierającego.  
  
## <a name="classes-and-modules"></a>Klasy i moduły  
 Te elementy mają wiele wspólnego, ale istnieją pewne ważne różnice.  
  
-   **Terminologia.** Poprzednie wersje języka Visual Basic rozpoznawały dwa typy modułów: *moduły klas* (pliki .cls) i *moduły standardowe* (pliki .bas). W bieżącej wersji są one nazywane odpowiednio *klasami* i *modułami*.  
  
-   **Udostępnione elementy członkowskie.** Można określić, czy udostępniany jest element członkowski klasy czy wystąpienia.  
  
-   **Orientacja obiektowa.** Klasy są zorientowane obiektowo, a moduły nie. Można utworzyć co najmniej jednego wystąpienia klasy. Aby uzyskać więcej informacji, zobacz temat [Obiekty i klasy](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `Class` instrukcji, aby zdefiniować klasę i kilku członków.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>Zobacz też  
 [Obiekty i klasy](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Struktury i klasy](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Instrukcja Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Instrukcja Module](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Instrukcja Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Okres istnienia obiektów: w jaki sposób obiekty są tworzone i niszczone](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Typy ogólne w Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Instrukcje: używanie klasy ogólnej](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
