---
title: 'Instrukcje: Implementowanie niestandardowych metod dostępu zdarzeń - C# przewodnik programowania'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: aaf58307cb4e33a1caa7b1ef8584fbb33decea3f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240076"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Instrukcje: Implementowanie niestandardowych metod dostępu zdarzeń (C# Programming Guide)
Zdarzenie jest specjalnym rodzajem multiemisji delegat, który można wywołać tylko z w ramach klasy, która jest zadeklarowana w. Kod klienta subskrybuje zdarzenie, podając odwołanie do metody, które powinny być używane, gdy zdarzenie jest uruchamiane. Te metody są dodawane do listy wywołań obiektu delegowanego przy użyciu metod dostępu zdarzeń, która jest podobna do metody dostępu właściwości, z tą różnicą, że metody dostępu zdarzeń są nazywane `add` i `remove`. W większości przypadków nie trzeba podać niestandardowych metod dostępu zdarzeń. Gdy nie niestandardowych metod dostępu zdarzeń są podane w kodzie, kompilator będzie dodać je automatycznie. Jednak w niektórych przypadkach może trzeba będzie podać niestandardowe zachowanie. Takiej sytuacji jest wyświetlana w temacie [jak:  Zdarzenia implementowania interfejsu](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak implementować niestandardowe zdarzenie dostępu add i remove. Chociaż może zastąpić dowolny kod wewnątrz metody dostępu, zaleca się blokowanie zdarzeń, aby dodać lub usunąć nowej metody obsługi zdarzeń.  
  
[!code-csharp[IDrawingObject.OnDraw](codesnippet/CSharp/how-to-implement-interface-events_1.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a>Zobacz też

- [Zdarzenia](../../../csharp/programming-guide/events/index.md)  
- [event](../../../csharp/language-reference/keywords/event.md)