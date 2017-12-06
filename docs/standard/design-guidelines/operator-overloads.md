---
title: "Przeciążenia operatorów"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ffd472a7c410bd541ea0382f05f7ed92acb0e688
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="operator-overloads"></a><span data-ttu-id="ba085-102">Przeciążenia operatorów</span><span class="sxs-lookup"><span data-stu-id="ba085-102">Operator Overloads</span></span>
<span data-ttu-id="ba085-103">Przeciążenia operatorów Zezwalaj typy framework się tak, jakby były w nim elementów podstawowych języka wbudowanych.</span><span class="sxs-lookup"><span data-stu-id="ba085-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="ba085-104">Dozwolone i w niektórych sytuacjach przydatne, przeciążenia operatora należy używać ostrożnie.</span><span class="sxs-lookup"><span data-stu-id="ba085-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="ba085-105">Istnieje wiele przypadków, w którym operator przeładowanie ma zostały użyte, takich jak uruchomienia framework Designer na operatory dla operacji, które powinny być proste metody.</span><span class="sxs-lookup"><span data-stu-id="ba085-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="ba085-106">Poniższe wskazówki powinny pomóc w określeniu, kiedy i jak użycie przeładowania operatora.</span><span class="sxs-lookup"><span data-stu-id="ba085-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="ba085-107">**X należy UNIKAĆ** Definiowanie przeciążenia operatora w typów, które powinny uznać, takich jak typy pierwotne (wbudowane).</span><span class="sxs-lookup"><span data-stu-id="ba085-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="ba085-108">**ROZWAŻ ✓** Definiowanie przeciążenia operatora w typie, który powinien uznać, takie jak typ pierwotny.</span><span class="sxs-lookup"><span data-stu-id="ba085-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="ba085-109">Na przykład <xref:System.String?displayProperty=nameWithType> ma `operator==` i `operator!=` zdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="ba085-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="ba085-110">**CZY ✓** definiować przeciążeń operatora w strukturach, które reprezentują numery (takie jak <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="ba085-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="ba085-111">**X nie** można cute podczas definiowania przeciążenia operatora.</span><span class="sxs-lookup"><span data-stu-id="ba085-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="ba085-112">Przeładowanie operatora jest przydatne w sytuacjach, w których jest od razu widoczne co wynik operacji będzie.</span><span class="sxs-lookup"><span data-stu-id="ba085-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="ba085-113">Na przykład, warto mieć możliwość odjąć jedną <xref:System.DateTime> z innego `DateTime` i uzyskać <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="ba085-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="ba085-114">Jednak nie jest odpowiedni, użyj logicznego operator union, union kwerend dwie bazy danych lub użyj operatora shift, aby zapisać do strumienia.</span><span class="sxs-lookup"><span data-stu-id="ba085-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="ba085-115">**X nie** Podaj operator overloads, chyba że jest co najmniej jeden z argumentów typu Definiowanie przeciążenia.</span><span class="sxs-lookup"><span data-stu-id="ba085-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="ba085-116">**CZY ✓** przeciążać operatory w sposób symetrycznego.</span><span class="sxs-lookup"><span data-stu-id="ba085-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="ba085-117">Na przykład, jeśli można przeciążać `operator==`, powinien także przeciążać `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="ba085-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="ba085-118">Podobnie jeśli można przeciążać `operator<`, powinien także przeciążać `operator>`i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="ba085-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="ba085-119">**ROZWAŻ ✓** zapewniając metod przyjaznych nazw, które odpowiadają do każdego przeciążonego operatora.</span><span class="sxs-lookup"><span data-stu-id="ba085-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="ba085-120">Przeładowanie operatora nie obsługują wiele języków.</span><span class="sxs-lookup"><span data-stu-id="ba085-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="ba085-121">Z tego powodu zaleca się, że typy, które przeciążać operatory obejmuje dodatkowej metody z odpowiednią nazwę specyficznego dla domeny, która udostępnia podobne funkcje.</span><span class="sxs-lookup"><span data-stu-id="ba085-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="ba085-122">Poniższa tabela zawiera listę operatory i metody przyjaznej nazwy.</span><span class="sxs-lookup"><span data-stu-id="ba085-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="ba085-123">Symbol operatora C#</span><span class="sxs-lookup"><span data-stu-id="ba085-123">C# Operator Symbol</span></span>|<span data-ttu-id="ba085-124">Nazwa metadanych</span><span class="sxs-lookup"><span data-stu-id="ba085-124">Metadata Name</span></span>|<span data-ttu-id="ba085-125">Przyjazna nazwa</span><span class="sxs-lookup"><span data-stu-id="ba085-125">Friendly Name</span></span>|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a><span data-ttu-id="ba085-126">Przeciążanie operatora ==</span><span class="sxs-lookup"><span data-stu-id="ba085-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="ba085-127">Przeciążanie `operator ==` jest dość złożone.</span><span class="sxs-lookup"><span data-stu-id="ba085-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="ba085-128">Semantyka operatora musi być zgodna z kilku innych elementach członkowskich, takich jak <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ba085-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="ba085-129">Operatory konwersji</span><span class="sxs-lookup"><span data-stu-id="ba085-129">Conversion Operators</span></span>  
 <span data-ttu-id="ba085-130">Operatory konwersji są operatory jednoargumentowe, umożliwiających konwersja z typu na inny.</span><span class="sxs-lookup"><span data-stu-id="ba085-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="ba085-131">Operatory musi być zdefiniowany jako statyczne elementy członkowskie na argument lub typ zwracany.</span><span class="sxs-lookup"><span data-stu-id="ba085-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="ba085-132">Istnieją dwa typy operatory konwersji: jawne i niejawne.</span><span class="sxs-lookup"><span data-stu-id="ba085-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="ba085-133">**X nie** Podaj operatora konwersji, jeśli takie konwersja nie jest wyraźnie oczekiwany przez użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="ba085-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="ba085-134">**X nie** definiować operatory konwersji poza domeny typu.</span><span class="sxs-lookup"><span data-stu-id="ba085-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="ba085-135">Na przykład <xref:System.Int32>, <xref:System.Double>, i <xref:System.Decimal> są wszystkie typy liczbowe, podczas gdy <xref:System.DateTime> nie jest.</span><span class="sxs-lookup"><span data-stu-id="ba085-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="ba085-136">W związku z tym nie powinny istnieć żaden operator konwersji, aby przekonwertować `Double(long)` do `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="ba085-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="ba085-137">W takim przypadku jest preferowane konstruktora.</span><span class="sxs-lookup"><span data-stu-id="ba085-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="ba085-138">**X nie** Podaj operator niejawnej konwersji, jeśli konwersja jest potencjalnie stratnej.</span><span class="sxs-lookup"><span data-stu-id="ba085-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="ba085-139">Na przykład nie należy niejawna konwersja z `Double` do `Int32` ponieważ `Double` ma większej niż `Int32`.</span><span class="sxs-lookup"><span data-stu-id="ba085-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="ba085-140">Operator jawnej konwersji można podać, nawet jeśli konwersja jest potencjalnie stratnej.</span><span class="sxs-lookup"><span data-stu-id="ba085-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="ba085-141">**X nie** zgłaszanie wyjątków z niejawnego rzutowania.</span><span class="sxs-lookup"><span data-stu-id="ba085-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="ba085-142">Jest bardzo trudne dla użytkowników końcowych zorientować się, ponieważ nie może być należy pamiętać, że konwersja jest wykonywana.</span><span class="sxs-lookup"><span data-stu-id="ba085-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="ba085-143">**CZY ✓** throw <xref:System.InvalidCastException?displayProperty=nameWithType> jeśli powoduje wywołanie operatora rzutowania stratnej konwersji i kontrakt operator nie zezwala stratnej konwersji.</span><span class="sxs-lookup"><span data-stu-id="ba085-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="ba085-144">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="ba085-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ba085-145">*Drukowane uprawnieniami wariancji x edukacji, Inc. z [Framework zaleceń dotyczących projektowania: konwencje, Idioms i wzorce dla bibliotek .NET wielokrotnego użytku, wydanie 2](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina i Abrams Brada opublikowane 22 Oct 2008 przez Professional Addison-Wesley jako część serii rozwoju systemu Windows firmy Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="ba085-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba085-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ba085-146">See Also</span></span>  
 [<span data-ttu-id="ba085-147">Wytyczne dotyczące projektowania elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="ba085-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="ba085-148">Wytyczne dotyczące projektowania Framework</span><span class="sxs-lookup"><span data-stu-id="ba085-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)