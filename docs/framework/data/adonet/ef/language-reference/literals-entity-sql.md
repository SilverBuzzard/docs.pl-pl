---
title: "Literały (jednostka SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 50edfb344177dbec8cff9609aeab56d1db762eb7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="literals-entity-sql"></a><span data-ttu-id="2810b-102">Literały (jednostka SQL)</span><span class="sxs-lookup"><span data-stu-id="2810b-102">Literals (Entity SQL)</span></span>
<span data-ttu-id="2810b-103">W tym temacie opisano [!INCLUDE[esql](../../../../../../includes/esql-md.md)] obsługę literały.</span><span class="sxs-lookup"><span data-stu-id="2810b-103">This topic describes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] support for literals.</span></span>  
  
## <a name="null"></a><span data-ttu-id="2810b-104">Null</span><span class="sxs-lookup"><span data-stu-id="2810b-104">Null</span></span>  
 <span data-ttu-id="2810b-105">Pusty literał jest używana do reprezentowania wartość null dla dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="2810b-105">The null literal is used to represent the value null for any type.</span></span> <span data-ttu-id="2810b-106">Pusty literał jest zgodny z dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="2810b-106">A null literal is compatible with any type.</span></span>  
  
 <span data-ttu-id="2810b-107">Wartości null bez typu mogą być tworzone przez rzutowanie za pośrednictwem literału null.</span><span class="sxs-lookup"><span data-stu-id="2810b-107">Typed nulls can be created by a cast over a null literal.</span></span> <span data-ttu-id="2810b-108">Aby uzyskać więcej informacji, zobacz [RZUTOWANIA](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2810b-108">For more information, see [CAST](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md).</span></span>  
  
 <span data-ttu-id="2810b-109">Dla reguły o tym, gdzie zwolnienia zmiennoprzecinkową literałów wartości null, mogą być używane, zobacz [literałów wartości Null i wnioskowanie o typie](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2810b-109">For rules about where free floating null literals can be used, see [Null Literals and Type Inference](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md).</span></span>  
  
## <a name="boolean"></a><span data-ttu-id="2810b-110">Boolean</span><span class="sxs-lookup"><span data-stu-id="2810b-110">Boolean</span></span>  
 <span data-ttu-id="2810b-111">Literałów wartości logicznych są reprezentowane przez słowa kluczowe `true` i `false`.</span><span class="sxs-lookup"><span data-stu-id="2810b-111">Boolean literals are represented by the keywords `true` and `false`.</span></span>  
  
## <a name="integer"></a><span data-ttu-id="2810b-112">Liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="2810b-112">Integer</span></span>  
 <span data-ttu-id="2810b-113">Literały całkowite może być typu <xref:System.Int32> lub <xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="2810b-113">Integer literals can be of type <xref:System.Int32> or <xref:System.Int64>.</span></span> <span data-ttu-id="2810b-114"><xref:System.Int32> Literału ciągu znaków liczbowych jest.</span><span class="sxs-lookup"><span data-stu-id="2810b-114">An <xref:System.Int32> literal is a series of numeric characters.</span></span> <span data-ttu-id="2810b-115"><xref:System.Int64> Literału jest szereg liczbową znaków, wielkie litery L.</span><span class="sxs-lookup"><span data-stu-id="2810b-115">An <xref:System.Int64> literal is series of numeric characters followed by an uppercase L.</span></span>  
  
## <a name="decimal"></a><span data-ttu-id="2810b-116">Wartość dziesiętna</span><span class="sxs-lookup"><span data-stu-id="2810b-116">Decimal</span></span>  
 <span data-ttu-id="2810b-117">Numer stałoprzecinkowe (dziesiętna) jest ciąg znaków liczbowych, kropkę (.) i innej serii liczbową znaków, wielkie litery "M".</span><span class="sxs-lookup"><span data-stu-id="2810b-117">A fixed-point number (decimal) is a series of numeric characters, a dot (.) and another series of numeric characters followed by an uppercase "M".</span></span>  
  
## <a name="float-double"></a><span data-ttu-id="2810b-118">Float, Double</span><span class="sxs-lookup"><span data-stu-id="2810b-118">Float, Double</span></span>  
 <span data-ttu-id="2810b-119">Podwójnej precyzji liczba zmiennoprzecinkowa jest szereg cyfry, kropki (.) oraz innej serii cyfr prawdopodobnie następuje wykładnik.</span><span class="sxs-lookup"><span data-stu-id="2810b-119">A double-precision floating point number is a series of numeric characters, a dot (.) and another series of numeric characters possibly followed by an exponent.</span></span> <span data-ttu-id="2810b-120">Opisie pojedynczego punktu numer (lub float) jest liczbą zmiennoprzecinkową podwójnej precyzji zmiennoprzecinkowa numer składnia następuje f małe litery.</span><span class="sxs-lookup"><span data-stu-id="2810b-120">A single-precisions floating point number (or float) is a double-precision floating point number syntax followed by the lowercase f.</span></span>  
  
## <a name="string"></a><span data-ttu-id="2810b-121">String</span><span class="sxs-lookup"><span data-stu-id="2810b-121">String</span></span>  
 <span data-ttu-id="2810b-122">Ciąg jest ciąg znaków ujęta w znaki cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="2810b-122">A string is a series of characters enclosed in quote marks.</span></span> <span data-ttu-id="2810b-123">Cudzysłowy może być albo obu pojedynczej oferty (`'`) lub obie podwójnych cudzysłowów (").</span><span class="sxs-lookup"><span data-stu-id="2810b-123">Quotes can be either both single-quotes (`'`) or both double-quotes (").</span></span> <span data-ttu-id="2810b-124">Literały ciągu znaków może być Unicode lub z systemem innym niż Unicode.</span><span class="sxs-lookup"><span data-stu-id="2810b-124">Character string literals can be either Unicode or non-Unicode.</span></span> <span data-ttu-id="2810b-125">Deklarowanie literałów jako Unicode ciąg znaków, prefiks literału z wielkimi literami "N".</span><span class="sxs-lookup"><span data-stu-id="2810b-125">To declare a character string literal as Unicode, prefix the literal with an uppercase "N".</span></span> <span data-ttu-id="2810b-126">Wartość domyślna to literałów ciągów znaków innych niż Unicode.</span><span class="sxs-lookup"><span data-stu-id="2810b-126">The default is non-Unicode character string literals.</span></span> <span data-ttu-id="2810b-127">Nie może istnieć bez spacji między N a ładunek literału ciągu, a N muszą być pisane wielkimi literami.</span><span class="sxs-lookup"><span data-stu-id="2810b-127">There can be no spaces between the N and the string literal payload, and the N must be uppercase.</span></span>  
  
```  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a><span data-ttu-id="2810b-128">DataGodzina</span><span class="sxs-lookup"><span data-stu-id="2810b-128">DateTime</span></span>  
 <span data-ttu-id="2810b-129">Literale datetime jest niezależna od ustawień regionalnych i składa się z części daty i czasu.</span><span class="sxs-lookup"><span data-stu-id="2810b-129">A datetime literal is independent of locale and is composed of a date part and a time part.</span></span> <span data-ttu-id="2810b-130">Części zarówno data i godzina są obowiązkowe i nie ma wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="2810b-130">Both date and time parts are mandatory and there are no default values.</span></span>  
  
 <span data-ttu-id="2810b-131">Część daty muszą mieć format: `YYYY` - `MM` - `DD`, gdzie `YYYY` jest wartością czterocyfrowy rok zakresu od 0001 do 9999, `MM` miesiąc od 1 do 12 i `DD` jest wartość dnia, który jest prawidłowy dla danego miesiąca `MM`.</span><span class="sxs-lookup"><span data-stu-id="2810b-131">The date part must have the format: `YYYY`-`MM`-`DD`, where `YYYY` is a four digit year value between 0001 and 9999, `MM` is the month between 1 and 12 and `DD` is the day value that is valid for the given month `MM`.</span></span>  
  
 <span data-ttu-id="2810b-132">Składnik godziny musi mieć format: `HH`:`MM`[:`SS`[.fffffff]], gdzie `HH` jest wartość godziny od 0 do 23, `MM` minuty wartość od 0 do 59 `SS` jest druga wartość od 0 do 59 i fffffff ułamkowych drugiej wartości od 0 do 9999999.</span><span class="sxs-lookup"><span data-stu-id="2810b-132">The time part must have the format: `HH`:`MM`[:`SS`[.fffffff]], where `HH` is the hour value between 0 and 23, `MM` is the minute value between 0 and 59, `SS` is the second value between 0 and 59 and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="2810b-133">Wszystkie zakresy wartości są włącznie.</span><span class="sxs-lookup"><span data-stu-id="2810b-133">All value ranges are inclusive.</span></span> <span data-ttu-id="2810b-134">Ułamkowych części sekundy są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="2810b-134">Fractional seconds are optional.</span></span> <span data-ttu-id="2810b-135">Sekund są opcjonalne, chyba że określono ułamkowych części sekundy; w takim przypadku sekund są wymagane.</span><span class="sxs-lookup"><span data-stu-id="2810b-135">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="2810b-136">Jeśli nie określono sekund lub ułamkowych części sekundy, wartości domyślnej równej zero zostanie użyty.</span><span class="sxs-lookup"><span data-stu-id="2810b-136">When seconds or fractional seconds are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="2810b-137">Może być dowolną liczbę spacji między DATETIME symbol i ładunek w postaci literału, ale nie nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="2810b-137">There can be any number of spaces between the DATETIME symbol and the literal payload, but no new lines.</span></span>  
  
```  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a><span data-ttu-id="2810b-138">Godzina</span><span class="sxs-lookup"><span data-stu-id="2810b-138">Time</span></span>  
 <span data-ttu-id="2810b-139">Literału czasu jest niezależne od ustawień regionalnych i składać się tylko części czasu.</span><span class="sxs-lookup"><span data-stu-id="2810b-139">A time literal is independent of locale and composed of a time part only.</span></span> <span data-ttu-id="2810b-140">Składnik godziny jest obowiązkowy i nie ma wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="2810b-140">The time part is mandatory and there is no default value.</span></span> <span data-ttu-id="2810b-141">Musi mieć format gg: mm [: SS [.fffffff]], gdzie HH jest wartość godziny od 0 do 23, minuty wartość od 0 do 59, SS jest druga wartość od 0 do 59, a fffffff jest ułamek druga wartość od 0 do 9999999.</span><span class="sxs-lookup"><span data-stu-id="2810b-141">It must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the second fraction value between 0 and 9999999.</span></span> <span data-ttu-id="2810b-142">Wszystkie zakresy wartości są włącznie.</span><span class="sxs-lookup"><span data-stu-id="2810b-142">All value ranges are inclusive.</span></span> <span data-ttu-id="2810b-143">Ułamkowych części sekundy są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="2810b-143">Fractional seconds are optional.</span></span> <span data-ttu-id="2810b-144">Sekund są opcjonalne, chyba że określono ułamkowych części sekundy; w takim przypadku sekund są wymagane.</span><span class="sxs-lookup"><span data-stu-id="2810b-144">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="2810b-145">Jeśli sekund lub ułamków nie są określone, wartością domyślną równą zero, zostanie użyty.</span><span class="sxs-lookup"><span data-stu-id="2810b-145">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="2810b-146">Może być dowolną liczbę spacji między symbol czasu i ładunek w postaci literału, ale nie nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="2810b-146">There can be any number of spaces between the TIME symbol and the literal payload, but no new lines.</span></span>  
  
```  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a><span data-ttu-id="2810b-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2810b-147">DateTimeOffset</span></span>  
 <span data-ttu-id="2810b-148">Literał datetimeoffset jest niezależne od ustawień regionalnych i składać się ze część daty, godziny i część dotyczącą przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="2810b-148">A datetimeoffset literal is independent of locale and composed of a date part, a time part, and an offset part.</span></span> <span data-ttu-id="2810b-149">Wszystkie daty, godziny i przesunięcia części są obowiązkowe i nie ma wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="2810b-149">All date, time, and offset parts are mandatory and there are no default values.</span></span> <span data-ttu-id="2810b-150">Data część musi mieć format RRRR-MM-DD, gdzie RRRR jest wartością czterocyfrowy rok zakresu od 0001 do 9999, miesiąc od 1 do 12, a DD jest wartość dnia, który jest prawidłowy dla danego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="2810b-150">The date part must have the format YYYY-MM-DD, where YYYY is a four digit year value between 0001 and 9999, MM is the month between 1 and 12, and DD is the day value that is valid for the given month.</span></span> <span data-ttu-id="2810b-151">Składnik godziny musi mieć format gg: mm [: SS [.fffffff]], gdzie HH jest wartość godziny między 0 a 23, MM minuty wartość między 0 a 59, SS jest druga wartość od 0 do 59 i fffffff jest ułamkowych drugiej wartości od 0 do 9999999.</span><span class="sxs-lookup"><span data-stu-id="2810b-151">The time part must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="2810b-152">Wszystkie zakresy wartości są włącznie.</span><span class="sxs-lookup"><span data-stu-id="2810b-152">All value ranges are inclusive.</span></span> <span data-ttu-id="2810b-153">Ułamkowych części sekundy są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="2810b-153">Fractional seconds are optional.</span></span> <span data-ttu-id="2810b-154">Sekund są opcjonalne, chyba że określono ułamkowych części sekundy; w takim przypadku sekund są wymagane.</span><span class="sxs-lookup"><span data-stu-id="2810b-154">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="2810b-155">Jeśli sekund lub ułamków nie są określone, wartością domyślną równą zero, zostanie użyty.</span><span class="sxs-lookup"><span data-stu-id="2810b-155">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span> <span data-ttu-id="2810b-156">Części przesunięcia musi mieć format {+ &#124;-} gg: mm, gdzie HH i MM mają takie samo znaczenie jak składnik godziny.</span><span class="sxs-lookup"><span data-stu-id="2810b-156">The offset part must have the format {+&#124;-}HH:MM, where HH and MM have the same meaning as in the time part.</span></span> <span data-ttu-id="2810b-157">Zakres przesunięcia, jednak musi należeć do zakresu od -14:00 i + 14:00</span><span class="sxs-lookup"><span data-stu-id="2810b-157">The range of the offset, however, must be between -14:00 and + 14:00</span></span>  
  
 <span data-ttu-id="2810b-158">Może być dowolną liczbę spacji między DATETIMEOFFSET symbol i ładunek w postaci literału, ale nie nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="2810b-158">There can be any number of spaces between the DATETIMEOFFSET symbol and the literal payload, but no new lines.</span></span>  
  
```  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
>  <span data-ttu-id="2810b-159">Nieprawidłowa wartość literału SQL jednostki można wykracza poza obsługiwanych zakresów dla CLR lub źródła danych.</span><span class="sxs-lookup"><span data-stu-id="2810b-159">A valid Entity SQL literal value can fall outside the supported ranges for CLR or the data source.</span></span> <span data-ttu-id="2810b-160">Może to spowodować wyjątek</span><span class="sxs-lookup"><span data-stu-id="2810b-160">This might result in an exception</span></span>  
  
## <a name="binary"></a><span data-ttu-id="2810b-161">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="2810b-161">Binary</span></span>  
 <span data-ttu-id="2810b-162">Literał ciągu binarnego jest sekwencją cyfry szesnastkowe rozdzielone apostrofy po słowie kluczowym binarnego lub symbol skrótu `X` lub `x`.</span><span class="sxs-lookup"><span data-stu-id="2810b-162">A binary string literal is a sequence of hexadecimal digits delimited by single quotes following the keyword binary or the shortcut symbol `X` or `x`.</span></span> <span data-ttu-id="2810b-163">Symbol skrótu `X` nie uwzględnia wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="2810b-163">The shortcut symbol `X` is case insensitive.</span></span> <span data-ttu-id="2810b-164">Zero lub więcej spacji między słowem kluczowym `binary` i wartości ciągu binarnego.</span><span class="sxs-lookup"><span data-stu-id="2810b-164">A zero or more spaces are allowed between the keyword `binary` and the binary string value.</span></span>  
  
 <span data-ttu-id="2810b-165">Znaki szesnastkowe są również bez uwzględniania wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="2810b-165">Hexadecimal characters are also case insensitive.</span></span> <span data-ttu-id="2810b-166">Jeśli literał składa się z nieparzysta liczba cyfr szesnastkowych, literał zostaną porównane do następnego nawet szesnastkową wartością cyfrową, prefiksu literal o szesnastkowego zero cyfr.</span><span class="sxs-lookup"><span data-stu-id="2810b-166">If the literal is composed of an odd number of hexadecimal digits, the literal will be aligned to the next even hexadecimal digit by prefixing the literal with a hexadecimal zero digit.</span></span> <span data-ttu-id="2810b-167">Nie ma żadnego limitu posiadanie na rozmiar ciągu binarnego.</span><span class="sxs-lookup"><span data-stu-id="2810b-167">There is no formal limit on the size of the binary string.</span></span>  
  
```  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a><span data-ttu-id="2810b-168">Identyfikator GUID</span><span class="sxs-lookup"><span data-stu-id="2810b-168">Guid</span></span>  
 <span data-ttu-id="2810b-169">A `GUID` Literał reprezentuje unikatowy identyfikator globalny.</span><span class="sxs-lookup"><span data-stu-id="2810b-169">A `GUID` literal represents a globally unique identifier.</span></span> <span data-ttu-id="2810b-170">Jest sekwencję utworzoną przez słowo kluczowe `GUID` następuje cyfry szesnastkowe w formularzu, znany jako *rejestru* format: 8-4-4-4-12 ujęta w apostrofy.</span><span class="sxs-lookup"><span data-stu-id="2810b-170">It is a sequence formed by the keyword `GUID` followed by hexadecimal digits in the form known as *registry* format: 8-4-4-4-12 enclosed in single quotes.</span></span> <span data-ttu-id="2810b-171">Cyfry szesnastkowe są bez uwzględniania wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="2810b-171">Hexadecimal digits are case insensitive.</span></span>  
  
 <span data-ttu-id="2810b-172">Może być dowolną liczbę spacji między symbol identyfikator GUID i ładunek w postaci literału, ale nie nowych wierszy.</span><span class="sxs-lookup"><span data-stu-id="2810b-172">There can be any number of spaces between the GUID symbol and the literal payload, but no new lines.</span></span>  
  
```  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a><span data-ttu-id="2810b-173">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2810b-173">See Also</span></span>  
 [<span data-ttu-id="2810b-174">Omówienie SQL jednostki</span><span class="sxs-lookup"><span data-stu-id="2810b-174">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)