---
title: 'Porady: tworzenie nieoznaczonych przyjaznych zestawów (C#)'
ms.date: 07/20/2015
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
ms.openlocfilehash: 7244f17c24a16569903783c730fc356b11e20aa8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211804"
---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a>Porady: tworzenie nieoznaczonych przyjaznych zestawów (C#)
W tym przykładzie pokazano, jak przyjaznych zestawów za pomocą zestawów, które są bez znaku.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Aby utworzyć zestaw i zestaw przyjazny  
  
1.  Otwórz wiersz polecenia.  
  
2.  Utwórz plik języka C# o nazwie `friend_signed_A.` zawierający poniższy kod. Kod używa <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybutu, aby zadeklarować friend_signed_B jako przyjaznego zestawu.  
  
    ```csharp  
    // friend_unsigned_A.cs  
    // Compile with:   
    // csc /target:library friend_unsigned_A.cs  
    using System.Runtime.CompilerServices;  
    using System;  
  
    [assembly: InternalsVisibleTo("friend_unsigned_B")]  
  
    // Type is internal by default.  
    class Class1  
    {  
        public void Test()  
        {  
            Console.WriteLine("Class1.Test");  
        }  
    }  
  
    // Public type with internal member.  
    public class Class2  
    {  
        internal void Test()  
        {  
            Console.WriteLine("Class2.Test");  
        }  
    }  
    ```  
  
3.  Skompiluj i podpisać friend_signed_A przy użyciu następującego polecenia.  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4.  Utwórz plik języka C# o nazwie `friend_unsigned_B` zawierający poniższy kod. Ponieważ friend_unsigned_A określa friend_unsigned_B jako zestaw przyjazny, kod w friend_unsigned_B mogą uzyskiwać dostęp do `internal` typów i elementów członkowskich z friend_unsigned_A.  
  
    ```csharp  
    // friend_unsigned_B.cs  
    // Compile with:   
    // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            // Access an internal type.  
            Class1 inst1 = new Class1();  
            inst1.Test();  
  
            Class2 inst2 = new Class2();  
            // Access an internal member of a public type.  
            inst2.Test();  
  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
5.  Skompiluj friend_signed_B przy użyciu następującego polecenia.  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     Nazwa zestawu, który jest generowany przez kompilator musi odpowiadać nazwy przyjaznego zestawu, który jest przekazywany do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybutu. Należy jawnie określić nazwę zestawu wyjściowego (.exe lub .dll), za pomocą `/out` — opcja kompilatora. Aby uzyskać więcej informacji, zobacz [/out (opcje kompilatora C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).  
  
6.  Uruchom plik friend_signed_B.exe.  
  
     Program wyświetla dwa ciągi: "Class1.Test" i "Class2.Test".  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Istnieją podobieństwa między usługami <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybutu i <xref:System.Security.Permissions.StrongNameIdentityPermission> klasy. Główną różnicą jest to, że <xref:System.Security.Permissions.StrongNameIdentityPermission> może wymagać uprawnienia zabezpieczeń do uruchamiania w określonej sekcji kodu, natomiast <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybut kontroluje widoczność `internal` typów i elementów członkowskich.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
- [Zestawy i Globalna pamięć podręczna zestawów (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
- [Przyjazne zestawy (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
- [Porady: tworzenie oznaczonych przyjaznych zestawów (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
- [Przewodnik programowania w języku C#](../../../../csharp/programming-guide/index.md)
