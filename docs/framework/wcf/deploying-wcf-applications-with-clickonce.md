---
title: "Wdrażanie aplikacji WCF za pomocą technologii ClickOnce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e7e419b1ca66e9d70b619e5841b8b984e06557f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="7f21a-102">Wdrażanie aplikacji WCF za pomocą technologii ClickOnce</span><span class="sxs-lookup"><span data-stu-id="7f21a-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="7f21a-103">Aplikacje klienckie przy użyciu [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] można wdrożyć przy użyciu technologii ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="7f21a-103">Client applications using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="7f21a-104">Ta technologia umożliwia im to wykorzystać środowiska uruchomieniowego ochrony zabezpieczeń dostarczone przez zabezpieczenia dostępu kodu, pod warunkiem, że są podpisane cyfrowo przy użyciu zaufanego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="7f21a-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="7f21a-105">Certyfikat używany do podpisywania aplikacji ClickOnce musi znajdować się w magazynie zaufanego wydawcy i zasady zabezpieczeń lokalnych na komputerze klienckim należy skonfigurować tak, aby udzielić uprawnień pełne zaufanie do wydawcy certyfikat podpisywania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7f21a-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="7f21a-106">Aby uzyskać informacje na temat konfigurowania aplikacji ClickOnce i zaufanych wydawców, zobacz [Konfigurowanie zaufanych wydawców ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="7f21a-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f21a-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7f21a-107">See Also</span></span>  
 [<span data-ttu-id="7f21a-108">Przegląd wdrażania zaufanych aplikacji</span><span class="sxs-lookup"><span data-stu-id="7f21a-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="7f21a-109">Wdrożenie ClickOnce dla systemu Windows formularzy aplikacji</span><span class="sxs-lookup"><span data-stu-id="7f21a-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)