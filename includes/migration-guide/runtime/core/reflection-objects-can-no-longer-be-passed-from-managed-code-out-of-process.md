### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Odbicie obiekty nie mogą być przekazywane z kodu zarządzanego, klientom DCOM spoza procesu

|   |   |
|---|---|
|Szczegóły|Obiekty odbicia już nie mogą być przekazywane z kodu zarządzanego do klientów modelu DCOM spoza procesu. Dotyczy następujących typów:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> (i jego typów pochodnych, w tym <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name>, i <xref:System.Reflection.TypeInfo?displayProperty=name>)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Wywołania <code>IMarshal</code> dla zwracanego obiektu <code>E_NOINTERFACE</code>.|
|Sugestia|Aktualizowanie kierowania kodu do pracy z obiektami bez odbicia|
|Zakres|Mały|
|Wersja|4.6|
|Typ|Środowisko uruchomieniowe|

