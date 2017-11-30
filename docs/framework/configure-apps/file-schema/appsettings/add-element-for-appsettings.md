---
title: '&lt;Dodaj&gt; elementu &lt;appSettings&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b00af6f7d735d5db8fd746205ba225253cad133
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="170df-102">\<Dodaj > elementu \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="170df-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="170df-103">Dodaje ustawienia aplikacji niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="170df-103">Adds a custom application setting.</span></span>

<span data-ttu-id="170df-104">[**\<Konfiguracja >**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="170df-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="170df-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="170df-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="170df-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Dodaj >**</span><span class="sxs-lookup"><span data-stu-id="170df-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="170df-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="170df-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="170df-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="170df-108">Attributes</span></span>

|           | <span data-ttu-id="170df-109">Opis</span><span class="sxs-lookup"><span data-stu-id="170df-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="170df-110">**klucz**</span><span class="sxs-lookup"><span data-stu-id="170df-110">**key**</span></span>   | <span data-ttu-id="170df-111">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="170df-111">Required attribute.</span></span><br><br><span data-ttu-id="170df-112">Określa nazwę klucz do dodania.</span><span class="sxs-lookup"><span data-stu-id="170df-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="170df-113">**wartość**</span><span class="sxs-lookup"><span data-stu-id="170df-113">**value**</span></span> | <span data-ttu-id="170df-114">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="170df-114">Required attribute.</span></span><br><br><span data-ttu-id="170df-115">Określa wartość klucz do dodania.</span><span class="sxs-lookup"><span data-stu-id="170df-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="170df-116">Element nadrzędny</span><span class="sxs-lookup"><span data-stu-id="170df-116">Parent element</span></span>

|     | <span data-ttu-id="170df-117">Opis</span><span class="sxs-lookup"><span data-stu-id="170df-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="170df-118">**\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="170df-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="170df-119">Zawiera ustawienia aplikacji niestandardowych, takich jak ścieżki plików, adresy URL usługi XML sieci Web lub inne informacje konfiguracji niestandardowej dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="170df-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="170df-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="170df-120">Child elements</span></span>

<span data-ttu-id="170df-121">Brak</span><span class="sxs-lookup"><span data-stu-id="170df-121">None</span></span>

## <a name="example"></a><span data-ttu-id="170df-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="170df-122">Example</span></span>

<span data-ttu-id="170df-123">Poniższy przykład przedstawia sposób Dodaj ustawienie Konfiguracja niestandardowa nazwa aplikacji:</span><span class="sxs-lookup"><span data-stu-id="170df-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="170df-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="170df-124">See also</span></span>

[<span data-ttu-id="170df-125">Schemat pliku konfiguracji dla programu .NET Framework</span><span class="sxs-lookup"><span data-stu-id="170df-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)