---
title: Dokumentacja interfejsu API WIF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d7ae7ef82d12c024441d01ef420bc9366e3c589d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="wif-api-reference"></a><span data-ttu-id="6536c-102">Dokumentacja interfejsu API WIF</span><span class="sxs-lookup"><span data-stu-id="6536c-102">WIF API Reference</span></span>
<span data-ttu-id="6536c-103">Klasy Windows Identity Foundation (WIF) są podzielone między następujące zestawy: `mscorlib` (mscorlib.dll) `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) i `System.ServiceModel` () System.ServiceModel.dll).</span><span class="sxs-lookup"><span data-stu-id="6536c-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="6536c-104">Ten temat zawiera linki do WIF obszary nazw i klasy, które każda przestrzeń nazw zawiera krótkie objaśnienia.</span><span class="sxs-lookup"><span data-stu-id="6536c-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6536c-105">Następujące `System.IdentityModel` przestrzenie nazw zawiera klasy, które implementują modelu tożsamości opartego na oświadczeniach WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, i <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6536c-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6536c-106">Począwszy od programu .NET Framework 4.5, usługi WCF modelu tożsamości opartego na oświadczeniach zostało zastąpione przez WIF.</span><span class="sxs-lookup"><span data-stu-id="6536c-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="6536c-107">Nie należy używać klas w tych trzech obszarach nazw podczas tworzenia rozwiązań opartych na WIF.</span><span class="sxs-lookup"><span data-stu-id="6536c-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-108">Zawiera klasy reprezentujące transformacje plików cookie, usługi tokenu zabezpieczeń i specjalnych czytników słownika XML.</span><span class="sxs-lookup"><span data-stu-id="6536c-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-109">Zawiera klasy udostępniające konfiguracji dla aplikacji i usług, utworzony przy użyciu systemu Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="6536c-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="6536c-110">Ustawienia w obszarze reprezentują klasy w tej przestrzeni nazw [ \<identityConfiguration >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="6536c-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-111">Zawiera klasy reprezentujące elementów w dokumencie metadanych federacji.</span><span class="sxs-lookup"><span data-stu-id="6536c-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-112">Zawiera klasy reprezentujące artefakty WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="6536c-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-113">Zawiera klasy, które są używane w scenariuszach, pasywnym (WS-Federation).</span><span class="sxs-lookup"><span data-stu-id="6536c-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="6536c-114">Zawiera także niektóre klasy, które reprezentują ustawienia w obszarze [ \<system.identityModel.services >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="6536c-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="6536c-115">Ustawienia w tym elemencie Konfigurowanie protokołu WS-Federation dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6536c-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="6536c-116">`System.IdentityModel.Services.Configuration` Przestrzeń nazw zawiera większość klas, które są używane do konfigurowania usługi WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="6536c-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-117">Zawiera klasy udostępniające konfigurowania WIF aplikacji, które korzystają z protokołu WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="6536c-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="6536c-118">Ustawienia w obszarze reprezentują klasy w tej przestrzeni nazw [ \<system.identityModel.services >](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="6536c-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="6536c-119">`System.IdentityModel.Services` Przestrzeń nazw zawiera także niektóre klasy, które są używane do konfigurowania usługi WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="6536c-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-120">Zawiera token obsługi specjalnych zabezpieczeń na scenariusze farmy sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6536c-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-121">Zawiera klasy reprezentujące tokeny zabezpieczające, obsługi tokenu zabezpieczeń i innych artefaktów tokenu zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="6536c-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-122">Zawiera klasy reprezentujące oświadczeń, tożsamości opartego na oświadczeniach podmiotów opartego na oświadczeniach i pozostałych artefaktów modelu tożsamości opartego na oświadczeniach.</span><span class="sxs-lookup"><span data-stu-id="6536c-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="6536c-123">Zawiera klasy reprezentujące WCF kontrakty, kanały, hosty usługi i pozostałych artefaktów, które są używane w scenariuszach (WS-Trust) active.</span><span class="sxs-lookup"><span data-stu-id="6536c-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="6536c-124">Ta przestrzeń nazw zawiera również klasy specyficznych do usługi Windows Communication Foundation (WCF) i które nie są używane przez WIF.</span><span class="sxs-lookup"><span data-stu-id="6536c-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6536c-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6536c-125">See Also</span></span>  
 [<span data-ttu-id="6536c-126">Odwołanie do konfiguracji WIF</span><span class="sxs-lookup"><span data-stu-id="6536c-126">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)  
 [<span data-ttu-id="6536c-127">Namespace mapowanie między WIF 3.5 i WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="6536c-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)