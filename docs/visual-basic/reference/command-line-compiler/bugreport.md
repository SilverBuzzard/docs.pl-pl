---
title: -bugreport —
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: e8366e1050217f3d993d510683252728aba0c3d9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527354"
---
# <a name="-bugreport"></a>-bugreport —
Tworzy plik, który można użyć, gdy plik jest raport o usterce.  
  
## <a name="syntax"></a>Składnia  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a>Argumenty  
  
|Termin|Definicja|  
|---|---|  
|`file`|Wymagane. Nazwa pliku, który będzie zawierał raport o usterce. Nazwę pliku należy ująć w znaki cudzysłowu (""), jeśli nazwa zawiera spację.|  
  
## <a name="remarks"></a>Uwagi  
 Poniższe informacje są dodawane do `file`:  
  
-   Kopiowanie wszystkich plików kodu źródłowego w kompilacji.  
  
-   Lista opcji kompilatora, używane w kompilacji.  
  
-   Informacje o wersji dotyczące kompilatora, środowisko uruchomieniowe języka wspólnego i systemu operacyjnego.  
  
-   Kompilator dane wyjściowe, jeśli istnieje.  
  
-   Opis problemu, dla którego jest wyświetlany monit.  
  
-   Opis sposobu Twoim zdaniem ten problem należy ustalić, dla którego jest wyświetlany monit.  
  
 Ponieważ kopiowanie wszystkich plików kodu źródłowego jest uwzględniony w `file`, może zajść potrzeba odtworzenia kodu (podejrzanych) wada najkrótszej program możliwe.  
  
> [!IMPORTANT]
>  `-bugreport` Opcja tworzy plik, który zawiera potencjalnie poufne informacje. Obejmuje to bieżący czas, wersja kompilatora [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] wersji, wersji systemu operacyjnego, nazwę użytkownika, argumenty wiersza polecenia za pomocą których kompilator zostało uruchomione, każdy kod źródłowy i binarną formę dowolnego odwołanie do zestawu. Ta opcja może zostać oceniony przez określenie opcji wiersza polecenia w pliku Web.config dla kompilacji po stronie serwera [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] aplikacji. Aby tego uniknąć, należy zmodyfikować plik Machine.config, aby uniemożliwić użytkownikom kompilacji na serwerze.  
  
 Jeśli ta opcja jest używana z `-errorreport:prompt`, `-errorreport:queue`, lub `-errorreport:send`, i aplikacji wystąpi błąd wewnętrzny kompilatora, informacje zawarte w `file` są wysyłane do firmy Microsoft Corporation. Te informacje pomagają inżynierów firmy Microsoft, Zidentyfikuj przyczynę błędu i może poprawić kolejnej wersji programu Visual Basic. Domyślnie żadne informacje nie są wysyłane do firmy Microsoft. Jednakże, gdy kompilujesz aplikację za pomocą `-errorreport:queue`, która jest domyślnie włączone, aplikacja zbiera raporty o błędach. Następnie kiedy loguje administratora komputera, systemu raportowania błędów wyświetli okno wyskakujące z umożliwiająca administratorowi przesłać do firmy Microsoft raporty o wszelkich błędach, które od czasu logowania.  
  
> [!NOTE]
>  `/bugreport` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilacji z wiersza polecenia.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kompiluje `T2.vb` i umieszczenie wszystkich informacji usługi raportowania błędów w pliku `Problem.txt`.  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [trustLevel elementu dla securityPolicy (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
