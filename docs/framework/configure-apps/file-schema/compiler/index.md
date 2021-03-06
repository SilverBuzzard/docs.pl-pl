---
title: Schemat ustawień kompilatora i dostawcy języka
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8992c9e47e2b62e90191a67fc7353e138502ebf1
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185670"
---
# <a name="compiler-and-language-provider-settings-schema"></a>Schemat ustawień kompilatora i dostawcy języka
Kompilator i ustawienia dostawcy języka Określ elementy kompilatora konfiguracji dla dostępnych dostawców języka. Każdy element konfiguracji kompilator określa kod nazwę typu dostawcy, parametry kompilatora obsługiwane nazwy języka i obsługiwane rozszerzenia plików.  
  
 .NET Framework definiuje ustawienia kompilatora początkowe w pliku konfiguracji komputera (Machine.config). Deweloperom i dostawcom kompilatora umożliwia dodanie ustawienia konfiguracji dla nowego <xref:System.CodeDom.Compiler.CodeDomProvider> implementacji. Użyj <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metody, można programowo wyliczyć języka ustawienia konfiguracji dostawcy i kompilator na komputerze.  
  
 [\<Konfiguracja > Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<System.CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<kompilatory >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<Kompilator >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<System.CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Określa ustawienia konfiguracyjne kompilatora dla dostępnych dostawców języka.|  
|[\<kompilatory >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Kontener dla elementów konfiguracji, kompilator; zawiera zero lub więcej [ \<kompilatora >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementów.|  
|[\<Kompilator >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Określa atrybuty kompilatora konfiguracji dostawcy języka.|  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano element kompilatora typowej konfiguracji.  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też  
- <xref:System.CodeDom.Compiler.CompilerInfo>  
- <xref:System.CodeDom.Compiler.CodeDomProvider>  
- [Schemat pliku konfiguracji](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [\<Kompilator > Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
