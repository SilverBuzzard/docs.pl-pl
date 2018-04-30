### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle teraz oczekuje wartości HWND

|   |   |
|---|---|
|Szczegóły|<xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> Wartość wprowadzona w programie .NET Framework 2.0 umożliwia aplikacji do zarejestrowania wartość uchwyt okna nadrzędnego w taki sposób, że elementów interfejsu użytkownika wymagane do uzyskania dostępu do klucza (takich jak numer PIN Monituj lub zgody okna dialogowego) zostanie otwarty jako element podrzędny określonego okna modalnego. Począwszy od aplikacji, które odnoszą się do .NET Framework 4.7 w aplikacji formularzy systemu Windows można ustawić <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> właściwości z kodem podobnie do następującej:<pre><code class="language-C#">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>W poprzednich wersjach programu .NET Framework, wartość powinna znajdować się <xref:System.IntPtr?displayProperty=name> reprezentujący lokalizacja w pamięci, której [HWND](https://msdn.microsoft.com/library/windows/desktop/aa383751.aspx#HWND) wartości znajdowały się. Ustawienie właściwości formularza. Obsługiwana w systemie Windows 7 i wcześniejszych wersjach nie miały wpływu, ale w systemie Windows 8 i nowszych wersjach jej wynikiem &quot; <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>: parametr jest nieprawidłowy.&quot;|
|Sugestia|Aby użyć uproszczonej formularza zaleca się aplikacji przeznaczonych dla platformy .NET 4.7 lub nowszego pragnący zarejestrować relacji okna nadrzędnego:<pre><code class="language-C#">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>Użytkownicy, którzy ma określone, czy poprawną wartość do przekazania się adres lokalizacji pamięci, która przechowywana wartość <code>form.Handle</code> można zrezygnować z Zmiana zachowania, ustawienia przełącznika AppContext <code>Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle</code> do <code>true</code>.<ol><li>Programowo ustawiając compat zmienia na AppContext, zgodnie z objaśnieniem [tutaj](http://blogs.msdn.com/b/dotnet/archive/2015/04/29/net-announcements-at-build-2015.aspx#dotnet46)</li><li>Dodając następujący wiersz do <code>&lt;runtime&gt;</code> sekcji w pliku app.config:</li></ol><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Z drugiej strony, użytkownicy, którzy chcą zgadzaj się na nowe zachowanie na środowiska uruchomieniowego .NET Framework 4.7, w przypadku obciążeń aplikacji w obszarze starsze wersje programu .NET Framework, można ustawić AppContext przełączyć się do <code>false</code>.|
|Zakres|Pomocnicza|
|Wersja|4.7|
|Typ|Przekierowania|
|Dotyczy interfejsów API|<ul><li><xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType></li></ul>|
