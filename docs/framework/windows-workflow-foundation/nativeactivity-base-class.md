---
title: Klasa bazowa NativeActivity
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: 40eff2e597763fd492b3051df1a91622e7a60672
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842038"
---
# <a name="nativeactivity-base-class"></a>Klasa bazowa NativeActivity

<xref:System.Activities.NativeActivity> jest klasą abstrakcyjną, przy użyciu Konstruktor chroniony. Podobnie jak <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> służy do zapisywania imperatywne zachowanie przez zaimplementowanie <xref:System.Activities.NativeActivity.Execute%2A> metody. W odróżnieniu od <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> ma dostęp do wszystkich funkcji narażonych środowiska uruchomieniowego przepływu pracy za pośrednictwem <xref:System.Activities.NativeActivityContext> obiekt przekazany do <xref:System.Activities.NativeActivity.Execute%2A> metody.

## <a name="using-nativeactivitycontext"></a>Za pomocą NativeActivityContext
 Funkcje środowiska wykonawczego przepływów pracy są dostępne z poziomu <xref:System.Activities.NativeActivity.Execute%2A> metody za pomocą elementów członkowskich `context` parametr typu <xref:System.Activities.NativeActivityContext>. Funkcje dostępne za pośrednictwem <xref:System.Activities.NativeActivityContext> obejmują następujące elementy:

-   Pobieranie i Ustawianie zmiennych i argumentów.

-   Planowanie działań podrzędnych za pomocą <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>

-   Trwa przerywanie wykonywania czynności za pomocą <xref:System.Activities.NativeActivityContext.Abort%2A>.

-   Anulowania wykonywania podrzędnych za pomocą <xref:System.Activities.NativeActivityContext.CancelChild%2A> i <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.

-   Dostęp do zakładki działania przy użyciu metody, takie jak <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, i <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.

-   Niestandardowe śledzenia funkcji przy użyciu <xref:System.Activities.CodeActivityContext.Track%2A>.

-   Dostęp do właściwości wykonania tego działania i wartości właściwości, za pomocą <xref:System.Activities.CodeActivityContext.GetProperty%2A> i <xref:System.Activities.NativeActivityContext.GetValue%2A>.

-   Planowanie akcji działania i funkcji przy użyciu <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> i <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a>Aby utworzyć niestandardowe działanie, która dziedziczy z elementu NativeActivity

1.  Otwórz program Visual Studio 2010.

2.  Wybierz **pliku**, **nowe**, a następnie **projektu**. Wybierz **Workflow 4.0** w obszarze **Visual C#** w **typów projektów** okna, a następnie wybierz **v2010** węzła. Wybierz **Biblioteka działań** w **szablony** okna. Nazwa nowego projektu HelloActivity.

3.  Kliknij prawym przyciskiem myszy Activity1.xaml w projekcie HelloActivity, a następnie wybierz pozycję **Usuń**.

4.  Kliknij prawym przyciskiem myszy projekt HelloActivity, a następnie wybierz pozycję **Dodaj**, a następnie **klasy**. Nazwa nowej klasy HelloActivity.cs.

5.  W pliku HelloActivity.cs, Dodaj następujący kod `using` dyrektywy.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6.  Wprowadź nowy dziedziczyć z klasy <xref:System.Activities.NativeActivity> przez dodanie klasy bazowej do deklaracji klasy.

    ```csharp
    class HelloActivity : NativeActivity
    ```

7.  Dodawanie funkcji do klasy, dodając <xref:System.Activities.NativeActivity.Execute%2A> metody.

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8.  Zastąp <xref:System.Activities.NativeActivity.CacheMetadata%2A> metody i wywołanie odpowiedniej metody Add umożliwiające wiedzieć o zmienne, argumenty, elementy podrzędne i delegatów działania niestandardowego środowiska uruchomieniowego przepływu pracy. Aby uzyskać więcej informacji, zobacz <xref:System.Activities.NativeActivityMetadata> klasy.

9. Użyj <xref:System.Activities.NativeActivityContext> obiektu, aby zaplanować zakładki. Zobacz <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> Aby uzyskać szczegółowe informacje dotyczące sposobu tworzenia, planowanie i wznowienie zakładki.

    ```
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```