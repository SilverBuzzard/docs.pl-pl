---
title: '&gt;= — Operator - C# odwołania'
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 34437742d33cff97e53c6dfb163df083e80d41f3
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655936"
---
# <a name="gt-operator-c-reference"></a>&gt;= — Operator (odwołanie w C#)

Operator relacyjny "większe lub równe" `>=` zwraca `true` Jeśli pierwszy argument operacji jest większa lub równa drugim argumentem `false` inaczej. Obsługa wszystkich typów liczbowych i wyliczenie `>=` operatora. Dla argumentów operacji tego samego [wyliczenia](../keywords/enum.md) typu, odpowiadające im wartości typu całkowitego podstawowej są porównywane.

> [!NOTE]
> Dla operatorów relacyjnych `==`, `>`, `<`, `>=`, i `<=`, jeśli dowolny z argumentów nie jest liczbą (<xref:System.Double.NaN?displayProperty=nameWithType> lub <xref:System.Single.NaN?displayProperty=nameWithType>) wynik operacji jest `false`. Oznacza to, że `NaN` wartość jest większe niż, mniejsze ani równy do żadnej innej `double` (lub `float`) wartość. Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Double.NaN?displayProperty=nameWithType> lub <xref:System.Single.NaN?displayProperty=nameWithType> artykule dotyczącym struktury.

W poniższym przykładzie pokazano użycie `>=` operator:

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Overloadability — operator

Typy zdefiniowane przez użytkownika może [przeciążenia](../keywords/operator.md) `>=` operatora. Jeśli typem przeciążenia operatora "większe lub równe" `>=`, należy także przeciążyć [operator "mniejsze niż lub równe"](less-than-equal-operator.md) `<=`.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz [relacyjne i badania typu operatory](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) części [ C# specyfikacji języka](../language-specification/index.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Operatory języka C#](index.md)
- [>, operator](greater-than-operator.md)
- [==, operator](equality-comparison-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
