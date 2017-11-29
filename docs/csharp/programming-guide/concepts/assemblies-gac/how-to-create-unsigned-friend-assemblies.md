---
title: "Porady: tworzenie nieoznaczonych przyjaznych zestawów (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 854df39394ef10bf2404fb3f762586fb102fba7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a><span data-ttu-id="5a4dd-102">Porady: tworzenie nieoznaczonych przyjaznych zestawów (C#)</span><span class="sxs-lookup"><span data-stu-id="5a4dd-102">How to: Create Unsigned Friend Assemblies (C#)</span></span>
<span data-ttu-id="5a4dd-103">Ten przykład przedstawia sposób użycia przyjaznych zestawów z zestawów, które nie mają znaku.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="5a4dd-104">Aby utworzyć zestaw i przyjaznego zestawu</span><span class="sxs-lookup"><span data-stu-id="5a4dd-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="5a4dd-105">Otwórz wiersz polecenia.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="5a4dd-106">Utwórz plik C# o nazwie `friend_signed_A.` zawierający następujący kod.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-106">Create a C# file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="5a4dd-107">W kodzie użyto <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybutu, aby zadeklarować friend_signed_B jako przyjaznego zestawu.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
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
  
3.  <span data-ttu-id="5a4dd-108">Skompiluj i podpisz friend_signed_A za pomocą następującego polecenia.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4.  <span data-ttu-id="5a4dd-109">Utwórz plik C# o nazwie `friend_unsigned_B` zawierający następujący kod.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-109">Create a C# file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="5a4dd-110">Ponieważ friend_unsigned_A określa friend_unsigned_B jako przyjaznego zestawu, może uzyskać dostęp przez kod friend_unsigned_B `internal` typów i członków z friend_unsigned_A.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `internal` types and members from friend_unsigned_A.</span></span>  
  
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
  
5.  <span data-ttu-id="5a4dd-111">Kompiluj friend_signed_B za pomocą następującego polecenia.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     <span data-ttu-id="5a4dd-112">Nazwa zestawu, który jest generowany przez kompilator musi odpowiadać nazwy przyjaznego zestawu, który jest przekazywany do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="5a4dd-113">Należy jawnie określić nazwę zestawu wyjściowego (.exe lub .dll) przy użyciu `/out` — opcja kompilatora.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-113">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span> <span data-ttu-id="5a4dd-114">Aby uzyskać więcej informacji, zobacz [/out (opcje kompilatora C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5a4dd-114">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
6.  <span data-ttu-id="5a4dd-115">Uruchom plik friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-115">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="5a4dd-116">Program drukuje dwóch ciągów: "Class1.Test" i "Class2.Test".</span><span class="sxs-lookup"><span data-stu-id="5a4dd-116">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5a4dd-117">Zabezpieczenia.NET Framework</span><span class="sxs-lookup"><span data-stu-id="5a4dd-117">.NET Framework Security</span></span>  
 <span data-ttu-id="5a4dd-118">Brak podobieństwa między usługami <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybutu i <xref:System.Security.Permissions.StrongNameIdentityPermission> klasy.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="5a4dd-119">Główną różnicą jest to, że <xref:System.Security.Permissions.StrongNameIdentityPermission> można zażądać uprawnienia zabezpieczeń do uruchomienia określonej części kodu, podczas gdy <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybut kontroluje widoczność `internal` typy i składniki.</span><span class="sxs-lookup"><span data-stu-id="5a4dd-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4dd-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5a4dd-120">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="5a4dd-121">Zestawy i Globalna pamięć podręczna zestawów (C#)</span><span class="sxs-lookup"><span data-stu-id="5a4dd-121">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="5a4dd-122">Przyjazne zestawy (C#)</span><span class="sxs-lookup"><span data-stu-id="5a4dd-122">Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="5a4dd-123">Porady: tworzenie oznaczonych przyjaznych zestawów (C#)</span><span class="sxs-lookup"><span data-stu-id="5a4dd-123">How to: Create Signed Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="5a4dd-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="5a4dd-124">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)