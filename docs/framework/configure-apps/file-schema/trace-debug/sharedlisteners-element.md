---
title: "&lt;sharedListeners&gt; — Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7ab96ad43248517dca99bff176be7edfab8d3ced
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltsharedlistenersgt-element"></a><span data-ttu-id="5825a-102">&lt;sharedListeners&gt; — Element</span><span class="sxs-lookup"><span data-stu-id="5825a-102">&lt;sharedListeners&gt; Element</span></span>
<span data-ttu-id="5825a-103">Zawiera nasłuchujących może odwoływać się wszystkie źródła lub element śledzenia.</span><span class="sxs-lookup"><span data-stu-id="5825a-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="5825a-104">Te odbiorniki nie otrzymują śladów domyślnie i nie jest możliwe pobrać te odbiorniki w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="5825a-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="5825a-105">Obiekty nasłuchujące zidentyfikowane jako udostępnione obiekty nasłuchujące można dodać do źródła lub śledzenie według nazwy.</span><span class="sxs-lookup"><span data-stu-id="5825a-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="5825a-106">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="5825a-106">\<configuration></span></span>  
<span data-ttu-id="5825a-107">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="5825a-107">\<system.diagnostics></span></span>  
<span data-ttu-id="5825a-108">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="5825a-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5825a-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="5825a-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5825a-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="5825a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5825a-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="5825a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5825a-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="5825a-112">Attributes</span></span>  
 <span data-ttu-id="5825a-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="5825a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5825a-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="5825a-114">Child Elements</span></span>  
  
|<span data-ttu-id="5825a-115">Element</span><span class="sxs-lookup"><span data-stu-id="5825a-115">Element</span></span>|<span data-ttu-id="5825a-116">Opis</span><span class="sxs-lookup"><span data-stu-id="5825a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5825a-117">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="5825a-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="5825a-118">Dodaje odbiornika do `sharedListeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="5825a-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5825a-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="5825a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5825a-120">Element</span><span class="sxs-lookup"><span data-stu-id="5825a-120">Element</span></span>|<span data-ttu-id="5825a-121">Opis</span><span class="sxs-lookup"><span data-stu-id="5825a-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="5825a-122">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5825a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5825a-123">Określa element root dla sekcji konfiguracji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5825a-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5825a-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5825a-124">Remarks</span></span>  
 <span data-ttu-id="5825a-125">Dodawanie do kolekcji udostępnione obiekty nasłuchujące odbiornik nie była active odbiornika.</span><span class="sxs-lookup"><span data-stu-id="5825a-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="5825a-126">Należy nadal można dodać go do źródła śledzenia lub śledzenia przez dodanie go do `Listeners` kolekcji dla tego elementu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="5825a-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="5825a-127">Klasy odbiornika w programie .NET Framework pochodzić od <xref:System.Diagnostics.TraceListener> klasy.</span><span class="sxs-lookup"><span data-stu-id="5825a-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="5825a-128">Ten element może być użyty w pliku konfiguracji komputera (Machine.config) i pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5825a-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5825a-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="5825a-129">Example</span></span>  
 <span data-ttu-id="5825a-130">Poniższy przykład przedstawia użycie `<sharedListeners>` elementu do dodania odbiornika `console` do `Listeners` kolekcji dla obu <xref:System.Diagnostics.TraceSource> i <xref:System.Diagnostics.Trace> klasy.</span><span class="sxs-lookup"><span data-stu-id="5825a-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="5825a-131">Odbiornik śledzenia konsoli zapisuje informacje śledzenia do konsoli za pomocą jednego wywołania <xref:System.Diagnostics.TraceSource> lub <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="5825a-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a><span data-ttu-id="5825a-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5825a-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="5825a-133">Schemat ustawień debugowania i śledzenia</span><span class="sxs-lookup"><span data-stu-id="5825a-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="5825a-134">Obiekty nasłuchujące śledzenia</span><span class="sxs-lookup"><span data-stu-id="5825a-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)