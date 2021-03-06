---
title: Operatory true i false - C# odwołania
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245748"
---
# <a name="true-and-false-operators-c-reference"></a>Operatory true i false (C# odwołania)

`true` Operator zwraca [bool](bool.md) wartość `true` do wskazania, że argument jest zdecydowanie true. `false` Operator zwraca `bool` wartość `true` do wskazania, że argument jest zdecydowanie false. `true` i `false` operatorów nie ma gwarancji uzupełniają się wzajemnie. Oznacza to, że oba `true` i `false` operator może zwrócić `bool` wartość `false` dla tego samego argumentu operacji. Jeśli typ definiuje jeden z dwóch operatorów, zdefiniuj również innego operatora.

Jeśli typ za pomocą zdefiniowanego `true` i `false` operatory [przeciążenia](operator.md) [operator logiczny OR](../operators/or-operator.md) `|` lub [logicznego operatora AND](../operators/and-operator.md) `&` w określony sposób, [warunkowego logicznego operatora OR](../operators/conditional-or-operator.md) `||` lub [warunkowego logicznego operatora AND](../operators/conditional-and-operator.md) `&&`, odpowiednio, mogą być obliczane dla argumentów typu. Aby uzyskać więcej informacji, zobacz [zdefiniowanych przez użytkownika operatorów logicznych warunkowych](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) części [ C# specyfikacji języka](../language-specification/index.md).

Typ za pomocą zdefiniowanego `true` operator może być typ wyniku wyrażenia warunkowego kontroli w [Jeśli](if-else.md), [czy](do.md), [podczas](while.md), i [ Aby uzyskać](for.md) instrukcji i [operator warunkowy `?:` ](../operators/conditional-operator.md). Aby uzyskać więcej informacji, zobacz [wyrażeń logicznych](~/_csharplang/spec/expressions.md#boolean-expressions) części [ C# specyfikacji języka](../language-specification/index.md).

> [!TIP]
> Użyj `bool?` typu, jeśli wymagana jest obsługa przechowywanymi w trzech logiki, na przykład podczas pracy z bazami danych, które obsługują przechowywanymi w trzech typu logicznego. Aby uzyskać więcej informacji, zobacz [bool? typu](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) części [przy użyciu typów dopuszczających wartości zerowe](../../programming-guide/nullable-types/using-nullable-types.md) artykułu.

Poniższy przykład przedstawia typ, który określa zarówno `true` i `false` operatorów. Ponadto przeciąża logicznego operatora AND `&` w taki sposób, że operator `&&` mogą być obliczane dla argumentów typu.

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

Zwróć uwagę, zachowanie short-circuiting `&&` operatora. Gdy `GetFuelLaunchStatus` metoda zwraca `LaunchStatus.Red`, drugi operand `&&` operator nie jest oceniany. To dlatego, że `LaunchStatus.Red` ma zdecydowanie wartość false. Następnie wynik logicznego i nie zależy od wartości drugiego operandu. Dane wyjściowe z przykładu jest następująca:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Operatory języka C#](../operators/index.md)
- [`true` literał](true-literal.md)
- [`false` literał](false-literal.md)