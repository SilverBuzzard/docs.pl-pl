---
title: "Używanie bibliotek pochodzących z częściowo zaufanego kodu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a452370df7c18f3e3f0190a14979099152485f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="using-libraries-from-partially-trusted-code"></a><span data-ttu-id="9568c-102">Używanie bibliotek pochodzących z częściowo zaufanego kodu</span><span class="sxs-lookup"><span data-stu-id="9568c-102">Using Libraries from Partially Trusted Code</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  <span data-ttu-id="9568c-103">Ten temat dotyczy zachowanie zestawy o silnych nazwach i ma zastosowanie tylko do [poziom 1](../../../docs/framework/misc/security-transparent-code-level-1.md) zestawów.</span><span class="sxs-lookup"><span data-stu-id="9568c-103">This topic addresses the behavior of strong-named assemblies and applies only to [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) assemblies.</span></span> <span data-ttu-id="9568c-104">[Kod o przezroczystym poziomie bezpieczeństwa, poziom 2](../../../docs/framework/misc/security-transparent-code-level-2.md) zestawów w [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] lub później nie dotyczy silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="9568c-104">[Security-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) assemblies in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later are not affected by strong names.</span></span> <span data-ttu-id="9568c-105">Aby uzyskać więcej informacji na temat zmian w systemie zabezpieczeń, zobacz [zmiany zabezpieczeń](../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="9568c-105">For more information about changes to the security system, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="9568c-106">Aplikacje odbierające mniej niż pełne zaufanie od ich hosta lub piaskownicy nie mogą wywoływać udostępnionego zarządzane bibliotek, chyba, że moduł zapisujący biblioteki w szczególności pozwala na ich za pośrednictwem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9568c-106">Applications that receive less than full trust from their host or sandbox are not allowed to call shared managed libraries unless the library writer specifically allows them to through the use of the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="9568c-107">W związku z tym zapisywania aplikacji należy pamiętać, że niektóre biblioteki nie będą dostępne do nich z kontekstu częściowo zaufany.</span><span class="sxs-lookup"><span data-stu-id="9568c-107">Therefore, application writers must be aware that some libraries will not be available to them from a partially trusted context.</span></span> <span data-ttu-id="9568c-108">Domyślnie, całego kodu, który jest wykonywany w częściowo zaufanym [piaskownicy](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) i nie znajduje się w listę zestawów pełnego zaufania jest częściowo zaufany.</span><span class="sxs-lookup"><span data-stu-id="9568c-108">By default, all code that executes in a partial-trust [sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) and is not in the list of full-trust assemblies is partially trusted.</span></span> <span data-ttu-id="9568c-109">Jeśli nie będzie można wykonać z kontekstu częściowo zaufany lub jest wywoływany przez kod częściowo zaufany kod, nie trzeba być zajmującym się z informacjami w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="9568c-109">If you do not expect your code to be executed from a partially trusted context or to be called by partially trusted code, you do not have to be concerned about the information in this section.</span></span> <span data-ttu-id="9568c-110">Jednak podczas pisania kodu, który musi współdziałać z częściowo zaufanego kodu lub nie działać w kontekście częściowo zaufany, należy rozważyć następujące czynniki:</span><span class="sxs-lookup"><span data-stu-id="9568c-110">However, if you write code that must interact with partially trusted code or operate from a partially trusted context, you should consider the following factors:</span></span>  
  
-   <span data-ttu-id="9568c-111">Biblioteki muszą być podpisane przy użyciu silnej nazwy, aby być współużytkowane przez wiele aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9568c-111">Libraries must be signed with a strong name in order to be shared by multiple applications.</span></span> <span data-ttu-id="9568c-112">Silne nazwy Zezwalaj swój kod, aby być umieszczone w globalnej pamięci podręcznej zestawów lub dodane do listy pełnego zaufania sandboxing <xref:System.AppDomain>, i konsumentów sprawdzić, czy z określonym wystąpieniem dostępu mobilnego faktycznie pochodzi z możesz zezwolić.</span><span class="sxs-lookup"><span data-stu-id="9568c-112">Strong names allow your code to be placed in the global assembly cache or added to the full-trust list of a sandboxing <xref:System.AppDomain>, and allow consumers to verify that a particular piece of mobile code actually originates from you.</span></span>  
  
-   <span data-ttu-id="9568c-113">Domyślnie o silnych nazwach [poziom 1](../../../docs/framework/misc/security-transparent-code-level-1.md) współużytkowanych bibliotekach wykonać niejawnej [LinkDemand](../../../docs/framework/misc/link-demands.md) dla pełnego zaufania automatycznie, bez zapisywania biblioteki konieczności wykonywania żadnych czynności.</span><span class="sxs-lookup"><span data-stu-id="9568c-113">By default, strong-named [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) shared libraries perform an implicit [LinkDemand](../../../docs/framework/misc/link-demands.md) for full trust automatically, without the library writer having to do anything.</span></span>  
  
-   <span data-ttu-id="9568c-114">Jeśli obiekt wywołujący nie ma pełnego zaufania, ale nadal próba wywołania takie biblioteki, środowisko uruchomieniowe zgłasza <xref:System.Security.SecurityException> i obiekt wywołujący nie może połączyć do biblioteki.</span><span class="sxs-lookup"><span data-stu-id="9568c-114">If a caller does not have full trust but still tries to call such a library, the runtime throws a <xref:System.Security.SecurityException> and the caller is not allowed to link to the library.</span></span>  
  
-   <span data-ttu-id="9568c-115">Aby wyłączyć automatyczne **LinkDemand** i zapobiec z został zgłoszony wyjątek, możesz umieścić **AllowPartiallyTrustedCallersAttribute** atrybut na zakres zestaw udostępnionego Biblioteka.</span><span class="sxs-lookup"><span data-stu-id="9568c-115">In order to disable the automatic **LinkDemand** and prevent the exception from being thrown, you can place the **AllowPartiallyTrustedCallersAttribute** attribute on the assembly scope of a shared library.</span></span> <span data-ttu-id="9568c-116">Ten atrybut umożliwia bibliotek ma być wywoływana z częściowo zaufanego kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="9568c-116">This attribute allows your libraries to be called from partially trusted managed code.</span></span>  
  
-   <span data-ttu-id="9568c-117">Częściowo zaufany kod, który uzyskuje dostęp do biblioteki z tym atrybutem jest nadal może ulec dodatkowe ograniczenia zdefiniowane przez <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="9568c-117">Partially trusted code that is granted access to a library with this attribute is still subject to further restrictions defined by the <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="9568c-118">Nie istnieje sposób programowy dla częściowo zaufanego kodu do wywoływania biblioteki, która nie ma **AllowPartiallyTrustedCallersAttribute** atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9568c-118">There is no programmatic way for partially trusted code to call a library that does not have the **AllowPartiallyTrustedCallersAttribute** attribute.</span></span>  
  
 <span data-ttu-id="9568c-119">Biblioteki, w których są prywatne do konkretnej aplikacji nie wymagają silnej nazwy lub **AllowPartiallyTrustedCallersAttribute** atrybutu i nie może odwoływać się potencjalnie złośliwy kod z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9568c-119">Libraries that are private to a specific application do not require a strong name or the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be referenced by potentially malicious code outside the application.</span></span> <span data-ttu-id="9568c-120">Taki kod jest chroniony przed niewłaściwym użyciem zamierzone lub przypadkowe częściowo zaufany kod przenośnych bez developer konieczności wykonywania żadnych dodatkowych działań.</span><span class="sxs-lookup"><span data-stu-id="9568c-120">Such code is protected against intentional or unintentional misuse by partially trusted mobile code without the developer having to do anything extra.</span></span>  
  
 <span data-ttu-id="9568c-121">Należy rozważyć jawne włączenie używany przez kod częściowo zaufany dla następujących typów kodu:</span><span class="sxs-lookup"><span data-stu-id="9568c-121">You should consider explicitly enabling use by partially trusted code for the following types of code:</span></span>  
  
-   <span data-ttu-id="9568c-122">Kod, który dokładnie przetestowano dla luk w zabezpieczeniach i jest zgodne z wytycznymi opisanego w [Secure wytyczne kodowania](../../../docs/standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="9568c-122">Code that has been diligently tested for security vulnerabilities and is in compliance with the guidelines described in [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md).</span></span>  
  
-   <span data-ttu-id="9568c-123">Biblioteki kodów o silnej nazwie, napisanych specjalnie dla scenariuszy częściowo zaufany.</span><span class="sxs-lookup"><span data-stu-id="9568c-123">Strong-named code libraries that are specifically written for partially trusted scenarios.</span></span>  
  
-   <span data-ttu-id="9568c-124">Wszystkie składniki (czy częściowo lub całkowicie zaufane) podpisany silną nazwą, która zostanie wywołana przez kod, który jest pobierany z Internetu.</span><span class="sxs-lookup"><span data-stu-id="9568c-124">Any components (whether partially or fully trusted) signed with a strong name that will be called by code that is downloaded from the Internet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9568c-125">Nie masz niektórych klas w bibliotece klas programu .NET Framework **AllowPartiallyTrustedCallersAttribute** atrybutu i nie może być wywoływana przez kod częściowo zaufany.</span><span class="sxs-lookup"><span data-stu-id="9568c-125">Some classes in the .NET Framework class library do not have the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be called by partially trusted code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9568c-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9568c-126">See Also</span></span>  
 [<span data-ttu-id="9568c-127">Zabezpieczenia dostępu kodu</span><span class="sxs-lookup"><span data-stu-id="9568c-127">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)