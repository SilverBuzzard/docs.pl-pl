---
title: Operator — słowo kluczowe - C# odwołania
ms.custom: seodec18
description: Dowiedz się, jak przeciążenia wbudowanym operatorem języka C#
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: cdc052da4457a59cc66848780e944ccf203acf39
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235601"
---
# <a name="operator-c-reference"></a>operator (odwołanie w C#)

Użyj `operator` — słowo kluczowe przeciążenia wbudowanym operatorem lub podać konwersja zdefiniowana przez użytkownika, w deklaracji klasy lub struktury.

Aby przeciążyć operator na niestandardowej klasy lub struktury, musisz utworzyć Deklaracja operatora w odpowiedniego typu. Deklaracja operatora, który przeciążenia wbudowanym operatorem języka C# musi spełniać następujące reguły:

- Obejmuje zarówno `public` i `static` modyfikator.
- Zawiera on `operator X` gdzie `X` to nazwa lub symbol operatora jest przeciążony.
- Operatory jednoargumentowe mieć jeden parametr, a operatory dwuargumentowe mają dwa parametry. W każdym przypadku co najmniej jeden parametr musi być taki sam jak klasy lub struktury, która deklaruje operator.

Aby uzyskać informacje na temat definiowania operatorów konwersji, zobacz [jawne](explicit.md) i [niejawne](implicit.md) artykuły — słowo kluczowe.

Aby uzyskać omówienie, które mogą być przeciążone operatory języka C#, zobacz [operatory z możliwością przeciążenia](../../programming-guide/statements-expressions-operators/overloadable-operators.md) artykułu.

## <a name="example"></a>Przykład

W poniższym przykładzie zdefiniowano `Fraction` typ, który reprezentuje cyfry ułamkowe. Przeciąża `+` i `*` operatory przeprowadzić ułamkowe Dodawanie i mnożenie, a także operator konwersji na to, że konwertuje `Fraction` typ `double` typu.

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [implicit](implicit.md)
- [explicit](explicit.md)
- [Operatory z możliwością przeciążenia](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [Instrukcje: Implementowanie zdefiniowanych przez użytkownika konwersji struktur](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
