---
title: "&lt;Dodaj&gt; elementu bypasslist — (ustawienia sieciowe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: eae909e2f70cfa045dd9a5c6b7496f112a59dc45
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-bypasslist-network-settings"></a><span data-ttu-id="022e9-102">&lt;Dodaj&gt; elementu bypasslist — (ustawienia sieciowe)</span><span class="sxs-lookup"><span data-stu-id="022e9-102">&lt;add&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="022e9-103">Dodaje adres IP lub nazwa DNS do Lista obejść serwerów proxy.</span><span class="sxs-lookup"><span data-stu-id="022e9-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="022e9-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="022e9-104">\<configuration></span></span>  
<span data-ttu-id="022e9-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="022e9-105">\<system.net></span></span>  
<span data-ttu-id="022e9-106">\<defaultProxy — ></span><span class="sxs-lookup"><span data-stu-id="022e9-106">\<defaultProxy></span></span>  
<span data-ttu-id="022e9-107">\<bypasslist — ></span><span class="sxs-lookup"><span data-stu-id="022e9-107">\<bypasslist></span></span>  
<span data-ttu-id="022e9-108">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="022e9-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="022e9-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="022e9-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="022e9-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="022e9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="022e9-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="022e9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="022e9-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="022e9-112">Attributes</span></span>  
  
|<span data-ttu-id="022e9-113">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="022e9-113">**Attribute**</span></span>|<span data-ttu-id="022e9-114">**Opis**</span><span class="sxs-lookup"><span data-stu-id="022e9-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="022e9-115">**adres**</span><span class="sxs-lookup"><span data-stu-id="022e9-115">**address**</span></span>|<span data-ttu-id="022e9-116">Wyrażenie regularne opisujące adresu IP lub nazwy DNS.</span><span class="sxs-lookup"><span data-stu-id="022e9-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="022e9-117">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="022e9-117">Child Elements</span></span>  
 <span data-ttu-id="022e9-118">Brak.</span><span class="sxs-lookup"><span data-stu-id="022e9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="022e9-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="022e9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="022e9-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="022e9-120">**Element**</span></span>|<span data-ttu-id="022e9-121">**Opis**</span><span class="sxs-lookup"><span data-stu-id="022e9-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="022e9-122">bypasslist —</span><span class="sxs-lookup"><span data-stu-id="022e9-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="022e9-123">Zawiera zestaw wyrażeń regularnych, opisujących adresów, które nie korzystają z serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="022e9-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="022e9-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="022e9-124">Remarks</span></span>  
 <span data-ttu-id="022e9-125">`add` Element wstawia wyrażeń regularnych opisujące adresy IP lub nazwy serwera DNS do listy adresów, które Obejdź serwer proxy.</span><span class="sxs-lookup"><span data-stu-id="022e9-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="022e9-126">Wartość `address` atrybutu powinna być wyrażenie regularne opisuje zestaw adresów IP lub nazwy hosta.</span><span class="sxs-lookup"><span data-stu-id="022e9-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="022e9-127">Należy zachować ostrożność podczas określania wyrażenia regularnego dla tego elementu.</span><span class="sxs-lookup"><span data-stu-id="022e9-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="022e9-128">Wyrażenie regularne "[a-z] +\\.contoso\\.com" dopasowań żadnego hosta w domenie contoso.com, ale również zgodna każdego hosta w domenie contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="022e9-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="022e9-129">Aby dopasować tylko na hoście w domenie contoso.com, użyj elementu zakotwiczenia ("$"): "[a-z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="022e9-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="022e9-130">Aby uzyskać więcej informacji na temat wyrażeń regularnych Zobacz. [Wyrażeń regularnych programu .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="022e9-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="022e9-131">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="022e9-131">Configuration Files</span></span>  
 <span data-ttu-id="022e9-132">Ten element może być użyty w pliku konfiguracji aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="022e9-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="022e9-133">Przykład</span><span class="sxs-lookup"><span data-stu-id="022e9-133">Example</span></span>  
 <span data-ttu-id="022e9-134">W następującym przykładzie dodano dwa adresy do obejścia listy.</span><span class="sxs-lookup"><span data-stu-id="022e9-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="022e9-135">Pierwszy pomija serwera proxy dla wszystkich serwerów w domenie contoso.com. drugi pomija serwera proxy dla wszystkich serwerów rozpoczyna którego adres IP z 192.168.</span><span class="sxs-lookup"><span data-stu-id="022e9-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="022e9-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="022e9-136">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="022e9-137">Schemat ustawień sieci</span><span class="sxs-lookup"><span data-stu-id="022e9-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)