---
title: 'Instrukcje: Użycie wywołania platformy do odtwarzania pliku Wave - C# przewodnik programowania'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 101cd6fa044e181cf6f993fbea642c9dffe04008
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236859"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>Instrukcje: Użycie wywołania platformy do odtwarzania pliku Wave (C# Programming Guide)
Poniższy przykład kodu C# ilustruje sposób użycia platform wywołania usług do odtwarzania pliku wave dźwięku w systemie operacyjnym Windows.  
  
## <a name="example"></a>Przykład  
 Ten przykładowy kod używa `DllImport` do zaimportowania `winmm.dll`firmy `PlaySound` metody punktu wejścia jako `Form1 PlaySound()`. W przykładzie przedstawiono prosty formularz Windows za pomocą przycisku. Kliknięcie przycisku otwiera standardowy system windows <xref:System.Windows.Forms.OpenFileDialog> okno dialogowe, tak aby mogli otworzyć plik, aby odtworzyć. Po wybraniu pliku wave jest odtwarzany za pomocą `PlaySound()` metody `winmm.dll` biblioteki. Aby uzyskać więcej informacji na temat tej metody, zobacz [przy użyciu funkcji PlaySound pliki Audio fali](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files). Przeglądaj i wybierz plik, który ma rozszerzenie wav, a następnie kliknij **Otwórz** do odtwarzania pliku wave przy użyciu platformy wywołania. Pole tekstowe pokazuje pełną ścieżkę pliku, który został wybrany.  
  
 **Otwartych plików** okno dialogowe jest filtrowana w celu wyświetlenia tylko pliki mające rozszerzenie wav przy zastosowaniu ustawień filtru:  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
### <a name="to-compile-the-code"></a>Aby skompilować kod  
  
1.  Utwórz nowy projekt aplikacji Windows w języku C# w programie Visual Studio i nadaj mu nazwę **WinSound**.  
  
2.  Skopiuj kod powyżej i Wklej zawartość `Form1.cs` pliku.  
  
3.  Skopiuj poniższy kod, a następnie wklej je `Form1.Designer.cs` pliku w `InitializeComponent()` metody, istniejący kod.  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Skompiluj i uruchom kod.  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Aby uzyskać więcej informacji, zobacz [zabezpieczeń na platformie .NET](../../../standard/security/index.md).  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)  
- [Przegląd współdziałania](../../../csharp/programming-guide/interop/interoperability-overview.md)  
- [Im bliżej wywołania platformy](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
- [Marshaling danych w wywołaniu platformy](../../../framework/interop/marshaling-data-with-platform-invoke.md)
