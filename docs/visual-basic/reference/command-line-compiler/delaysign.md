---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 1459484b858137836fcfdcd9db46d8e99a06e9c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185212"
---
# <a name="-delaysign"></a>-delaysign
Określa, czy zestaw zostanie podpisany całkowicie czy częściowo.  
  
## <a name="syntax"></a>Składnia  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argumenty  
 `+` &#124; `-`  
 Opcjonalna. Użyj `-delaysign-` Jeśli chcesz, aby podpisać zestaw całkowicie. Użyj `-delaysign+` Jeśli chcesz umieścić klucz publiczny w zestaw i rezerwa ilości miejsca na skrót podpisanego. Wartość domyślna to `-delaysign-`.  
  
## <a name="remarks"></a>Uwagi  
 `-delaysign` Opcja nie ma wpływu, chyba że używana z [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) lub [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 W przypadku żądania całkowicie podpisanego zestawu, kompilator tworzy skrót pliku który zawiera manifest (metadane zestawu) i podpisuje skrót przy użyciu klucza prywatnego. Wynikowy podpis cyfrowy jest przechowywany w pliku, który zawiera manifest. Gdy zestaw jest podpisany z opóźnieniem, kompilator nie obliczanie oraz przechowywanie miejsce na podpis, ale rezerwy w pliku, aby podpis mógł zostać dodany później.  
  
 Na przykład za pomocą `-delaysign+`, Deweloper w organizacji mogą dystrybuować testu niepodpisane wersje zestawu, który testerów może rejestrować z globalnej pamięci podręcznej i używać. Po zakończeniu pracy w zestawie osoba odpowiedzialna za klucz prywatny organizacji można całkowicie podpisać zestaw. Ta segmentacji poszczególnych chroni klucz prywatny organizacji przed ujawnieniem, pozwalając wszystkich deweloperów pracowało nad zestawów.  
  
 Zobacz [tworzenie i zestawy Using Strong-Named](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) więcej informacji na temat podpisywania zestawu.  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Aby ustawić delaysign — w programie Visual Studio zintegrowane środowisko projektowe  
  
1.  Projekt wybrany w **Eksploratora rozwiązań**. Na **projektu** menu, kliknij przycisk **właściwości**.   
  
2.  Kliknij przycisk **podpisywanie** kartę.  
  
3.  Ustaw wartość w **opóźnienie logowania tylko** pole.  
  
## <a name="see-also"></a>Zobacz też  
 [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
