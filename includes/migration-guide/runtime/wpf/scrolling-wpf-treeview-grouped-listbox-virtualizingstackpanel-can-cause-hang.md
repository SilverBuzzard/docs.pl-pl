### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Przewijanie w widoku drzewa w WPF lub ListBox zgrupowane w VirtualizingStackPanel może spowodować zawieszenie

|   |   |
|---|---|
|Szczegóły|W wersji w .NET Framework 4.5., przewijania WPF <xref:System.Windows.Controls.TreeView?displayProperty=name> w zwirtualizowanych stack panel może spowodować zawiesza się, w przypadku marginesów w okienku ekranu (między elementami w <xref:System.Windows.Controls.TreeView?displayProperty=name>, na przykład, lub w elemencie ItemsPresenter). Ponadto w niektórych przypadkach różnych wielkości elementów w widoku może spowodować niestabilność, nawet jeśli nie mają żadnych marginesy.|
|Sugestia|Po uaktualnieniu do programu .NET Framework 4.5.1 można uniknąć tego błędu. Alternatywnie marginesy można usunąć z kolekcji widoku (takich jak <xref:System.Windows.Controls.TreeView?displayProperty=name>s) w ramach zwirtualizowanych stosu paneli, jeśli wszystkie zawarte elementy mają taki sam rozmiar.|
|Zakres|Duży|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|
|Dotyczy interfejsów API|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|

