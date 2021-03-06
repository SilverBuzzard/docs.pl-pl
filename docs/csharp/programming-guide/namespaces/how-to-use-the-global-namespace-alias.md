---
title: 'Instrukcje: Użycie globalnych aliasów Namespace - C# przewodnik programowania'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: 19d8d20ae630573b44399f8f5c5351f02b9fb1df
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236612"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>Instrukcje: Użycie globalnych aliasów Namespace (C# Programming Guide)
Możliwość dostępu do elementu członkowskiego w globalnym [przestrzeni nazw](../../../csharp/language-reference/keywords/namespace.md) jest przydatne, gdy element członkowski może być ono ukryte przez inną jednostkę o takiej samej nazwie.  
  
 Na przykład w poniższym kodzie `Console` jest rozpoznawana jako `TestApp.Console` zamiast do `Console` wpisać <xref:System> przestrzeni nazw.  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 Za pomocą `System.Console` nadal powoduje błąd, ponieważ `System` przestrzeni nazw jest ukryty przez klasę `TestApp.System`:  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 Jednak możesz obejść ten błąd, za pomocą `global::System.Console`, podobnie do następującego:  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 Gdy jest identyfikator po lewej stronie `global`, wyszukaj identyfikator prawo rozpoczyna się w globalnej przestrzeni nazw. Na przykład następująca deklaracja odwołuje się do `TestApp` jako członek globalnej przestrzeni.  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 Oczywiście, tworząc własne przestrzenie nazw o nazwie `System` nie jest zalecane, i jest mało prawdopodobne, będą napotykać jakiegokolwiek kodu, w którym to się stało. Jednak w dużych projektach, jest bardzo prawdziwy możliwość, że duplikacji przestrzeni nazw może wystąpić w czy innej formie. W takich sytuacjach kwalifikator globalnej przestrzeni nazw jest usługi gwarancji, że można określić głównej przestrzeni nazw.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie obszar nazw `System` jest używana do włączenia klasy `TestClass` w związku z tym, `global::System.Console` musi być używana do odwołania `System.Console` klasy, która jest ukryta przez `System` przestrzeni nazw. Ponadto alias `colAlias` służy do odwoływania się do przestrzeni nazw `System.Collections`; w związku z tym, wystąpienie <xref:System.Collections.Hashtable?displayProperty=nameWithType> został utworzony za pomocą tego aliasu zamiast przestrzeni nazw.  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
**1**
**B 2**
**C 3**

## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [Przestrzenie nazw](../../../csharp/programming-guide/namespaces/index.md)  
- [. operator](../../../csharp/language-reference/operators/member-access-operator.md)  
- [:: operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [extern](../../../csharp/language-reference/keywords/extern.md)
