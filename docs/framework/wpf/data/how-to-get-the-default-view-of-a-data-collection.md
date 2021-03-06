---
title: Jak pobrać domyślny widok kolekcji danych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e8e6928391a98a132f1dbb39edfda0d73d2eebdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557176"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Jak pobrać domyślny widok kolekcji danych
Widoki zezwolić tej samej kolekcji danych do wyświetlenia na różne sposoby, w zależności od sortowania, filtrowania lub kryteria grupowania. Każdy kolekcja zawiera jeden widok domyślny udostępnionego, który jest używany jako źródło rzeczywistego powiązania, gdy powiązanie Określa kolekcję jako źródło. W tym przykładzie przedstawiono sposób wyświetlania domyślnej kolekcji.  
  
## <a name="example"></a>Przykład  
 Aby utworzyć widok, należy odwołanie do obiektu do kolekcji. Ten obiekt danych można uzyskać za pomocą odwołań do własnego obiektu związane z kodem, pobierając kontekstu danych przez pobieranie właściwości źródła danych lub pobieranie właściwości powiązania. W tym przykładzie pokazano, jak pobrać <xref:System.Windows.FrameworkElement.DataContext%2A> obiekt danych i użyj go bezpośrednio uzyskać domyślnej kolekcji wyświetlania dla tej kolekcji.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 W tym przykładzie jest elementem głównym <xref:System.Windows.Controls.StackPanel>. <xref:System.Windows.FrameworkElement.DataContext%2A> Ustawiono *myDataSource*, które odwołuje się do dostawcy danych, który jest <xref:System.Collections.ObjectModel.ObservableCollection%601> z *kolejności* obiektów.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Alternatywnie można utworzyć wystąpienia i powiąż własnych kolekcji widoku przy użyciu <xref:System.Windows.Data.CollectionViewSource> klasy. Ten widok kolekcji jest udostępniany tylko przez formanty, które wiążą się do niego bezpośrednio. Na przykład zobacz sposób tworzenia widoku w sekcji [omówienie powiązania danych](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Aby uzyskać przykłady pokazujące funkcje udostępniane przez widok kolekcji, zobacz [sortowanie danych w widoku](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [filtrowanie danych w widoku](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), i [przejdź do obiektów w danych widoku CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Sortowanie i grupowanie danych przy użyciu widoku w XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Tematy z instrukcjami](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
