---
title: Federacja i zaufanie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: federation [WCF], and trust
ms.assetid: 4bdec4f2-f8a2-4512-bdcf-14ef54b5877a
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: db5ac2f0f85355e0163805bd0bb348bb54913c0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="federation-and-trust"></a><span data-ttu-id="0c958-102">Federacja i zaufanie</span><span class="sxs-lookup"><span data-stu-id="0c958-102">Federation and Trust</span></span>
<span data-ttu-id="0c958-103">W tym temacie opisano różne aspekty związane z aplikacji federacyjnych, granice zaufania i Konfiguracja i użycie wystawionych tokenów w [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c958-103">This topic covers various aspects related to federated applications, trust boundaries and configuration, and use of issued tokens in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="services-security-token-services-and-trust"></a><span data-ttu-id="0c958-104">Usługi, usługi tokenu zabezpieczeń i zaufania</span><span class="sxs-lookup"><span data-stu-id="0c958-104">Services, Security Token Services, and Trust</span></span>  
 <span data-ttu-id="0c958-105">Usługi, które zwykle ekspozycji punktów końcowych, federacyjnych oczekiwać klientów do uwierzytelniania za pomocą dostarczonych przez konkretnego wystawcę tokenu.</span><span class="sxs-lookup"><span data-stu-id="0c958-105">Services that expose federated endpoints typically expect clients to authenticate using a token provided by a specific issuer.</span></span> <span data-ttu-id="0c958-106">Należy pamiętać, że usługa jest skonfigurowana przy użyciu poprawnych poświadczeń wystawcy; w przeciwnym razie nie będzie możliwe do weryfikowania podpisów za pośrednictwem wystawionych tokenów, a klient będzie mogła nawiązać połączenia z usługą.</span><span class="sxs-lookup"><span data-stu-id="0c958-106">It is important that the service is configured with the correct credentials for the issuer; otherwise, it will not be able to verify signatures over the issued tokens, and the client will be unable to communicate with the service.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0c958-107">Konfigurowanie poświadczeń wystawcy na usługi, zobacz [porady: Konfigurowanie poświadczeń usługi federacyjnej](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="0c958-107"> configuring issuer credentials on the service, see [How to: Configure Credentials on a Federation Service](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
 <span data-ttu-id="0c958-108">Podobnie przy użyciu kluczy symetrycznych, kluczy szyfrowania dla usługi docelowej, należy skonfigurować usługę tokenu zabezpieczającego z prawidłowymi poświadczeniami dla usługi docelowej; w przeciwnym razie będzie nie można zaszyfrować klucza dla usługi docelowej, a następnie ponownie, klient będzie mogła nawiązać połączenia z usługą.</span><span class="sxs-lookup"><span data-stu-id="0c958-108">Similarly, when using symmetric keys, the keys are encrypted for the target service, so you must configure the security token service with the correct credentials for the target service; otherwise, it will be unable to encrypt the key for the target service, and again, the client will be unable to communicate with the service.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c958-109">usługi używają wartości <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> właściwość [SecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md) umożliwiające zegara pochylenia między klientem a usługą.</span><span class="sxs-lookup"><span data-stu-id="0c958-109"> services use the value of the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the [SecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md) to allow for clock skew between the client and service.</span></span> <span data-ttu-id="0c958-110">W Federacji `MaxClockSkew` ustawienie dotyczy pochyla zegara między zarówno klient, jak i usługi tokenu zabezpieczeń, z którym klient uzyskał wystawionego tokenu.</span><span class="sxs-lookup"><span data-stu-id="0c958-110">In federation, the `MaxClockSkew` setting applies to clock skews between both the client and the security token service from where the client obtained the issued token.</span></span> <span data-ttu-id="0c958-111">W związku z tym usługi tokenu zabezpieczeń nie muszą wprowadzać dodatki niedokładność zegara, ustawiając czas wejścia w życie i wygaśnięcia wystawionego tokenu.</span><span class="sxs-lookup"><span data-stu-id="0c958-111">Therefore, security token services need not make clock-skew allowances when setting the issued token's effective and expiration times.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c958-112">Ważność zegara zwiększa skraca czas istnienia wystawionego tokenu.</span><span class="sxs-lookup"><span data-stu-id="0c958-112">The importance of clock skew increases as the lifetime of the issued token shortens.</span></span> <span data-ttu-id="0c958-113">W większości przypadków niedokładność zegara nie jest znaczny problem, jeśli okres istnienia tokenu jest 30 minut lub dłużej.</span><span class="sxs-lookup"><span data-stu-id="0c958-113">In most cases, clock skew is not a significant issue if the token lifetime is 30 minutes or more.</span></span> <span data-ttu-id="0c958-114">Scenariusze z krótsze okresy istnienia lub których okres ważności dokładnego tokenu jest ważna należy tak zaprojektować uwzględnienie zegara pochylenia.</span><span class="sxs-lookup"><span data-stu-id="0c958-114">Scenarios with shorter lifetimes or where the exact validity time of the token is important should be designed to take clock skew into account.</span></span>  
  
## <a name="federated-endpoints-and-time-outs"></a><span data-ttu-id="0c958-115">Punkty końcowe federacyjnych i limity czasu</span><span class="sxs-lookup"><span data-stu-id="0c958-115">Federated Endpoints and Time-Outs</span></span>  
 <span data-ttu-id="0c958-116">Gdy klient komunikuje się z punktem końcowym federacyjnych, go najpierw uzyskać odpowiednią tokenu z usługi tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="0c958-116">When a client communicates with a federated endpoint, it must first acquire an appropriate token from a security token service.</span></span> <span data-ttu-id="0c958-117">Jeśli usługa tokenu zabezpieczającego przedstawia federacyjnych punktu końcowego, klient najpierw uzyskać tokenu od wystawcy dla tego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="0c958-117">If the security token service exposes a federated endpoint, the client must first obtain a token from the issuer for that endpoint.</span></span> <span data-ttu-id="0c958-118">Każdy token nabycia czas, i mogą ulec ogólny limit czasu dla wysyłania komunikatu rzeczywiste do końcowego punktu końcowego tego czasu.</span><span class="sxs-lookup"><span data-stu-id="0c958-118">Each token acquisition takes time, and that time is subject to the overall time-out for sending the actual message to the final endpoint.</span></span>  
  
 <span data-ttu-id="0c958-119">Na przykład limit czasu kanału po stronie klienta wynosi 30 sekund.</span><span class="sxs-lookup"><span data-stu-id="0c958-119">For example, the time-out on the client-side channel is set to 30 seconds.</span></span> <span data-ttu-id="0c958-120">Dwa wystawców tokenów muszą zostać wywołane pobranie tokenów przed wysłaniem wiadomości do końcowego punktu końcowego, a każdy trwa 15 sekund wystawianie tokenów.</span><span class="sxs-lookup"><span data-stu-id="0c958-120">Two token issuers need to be called to retrieve tokens before sending the message to the final endpoint, and each takes 15 seconds to issue a token.</span></span> <span data-ttu-id="0c958-121">W takim przypadku nie powiedzie się i <xref:System.TimeoutException> jest generowany.</span><span class="sxs-lookup"><span data-stu-id="0c958-121">In this case, the attempt will fail and a <xref:System.TimeoutException> is thrown.</span></span> <span data-ttu-id="0c958-122">W związku z tym należy ustawić <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> wartość kanału klienta do wartości wystarczająco duży, by uwzględnić czas, w celu pobrania wszystkich wystawionych tokenów.</span><span class="sxs-lookup"><span data-stu-id="0c958-122">Thus, you need to set the <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> value on the client channel to a value large enough to include the time taken to retrieve all issued tokens.</span></span> <span data-ttu-id="0c958-123">W przypadku, gdy nie określono wartości dla <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> właściwość <xref:System.ServiceModel.Channels.Binding.OpenTimeout%2A> właściwości lub <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A> właściwości (lub obie) musi być ustawiona na wartość wystarczająco duży, aby uwzględnić czas potrzebny na pobranie wszystkich wystawionych tokenów.</span><span class="sxs-lookup"><span data-stu-id="0c958-123">In the case where a value is not specified for the <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> property, the <xref:System.ServiceModel.Channels.Binding.OpenTimeout%2A> property or the <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A> property (or both) need to be set to a value large enough to include the time taken to retrieve all issued tokens.</span></span>  
  
## <a name="token-lifetime-and-renewal"></a><span data-ttu-id="0c958-124">Okres istnienia tokenu i odnawiania</span><span class="sxs-lookup"><span data-stu-id="0c958-124">Token Lifetime and Renewal</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c958-125">Klienci nie zaznaczaj wystawiony token początkowej żądaniu skierowanym do usługi.</span><span class="sxs-lookup"><span data-stu-id="0c958-125"> clients do not check the issued token when making an initial request to a service.</span></span>  <span data-ttu-id="0c958-126">Zamiast [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relacje zaufania usługi tokenu zabezpieczającego wystawianie tokenów z właściwym czasie aktywacji i ważności.</span><span class="sxs-lookup"><span data-stu-id="0c958-126">Rather, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trusts the security token service to issue a token with appropriate effective and expiration times.</span></span> <span data-ttu-id="0c958-127">Jeśli token jest buforowana przez klienta i użyć ponownie, okres istnienia tokenu jest zaznaczony na kolejnych żądań i w razie potrzeby klient automatycznie odnawia tokenu.</span><span class="sxs-lookup"><span data-stu-id="0c958-127">If the token is cached by the client and reused, the token lifetime is checked on subsequent requests and the client automatically renews the token if necessary.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0c958-128">Token buforowania, zobacz [porady: Tworzenie klienta federacyjnego](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="0c958-128"> token caching, see [How to: Create a Federated Client](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
 <span data-ttu-id="0c958-129">Określenie krótkich okresów istnienia, w kolejności wynoszącą 30 sekund lub mniej wystawione tokeny lub tokenów kontekstów zabezpieczeń, może spowodować negocjacji przekroczeń limitu czasu lub inne wyjątki zgłaszane przez [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klientów podczas żądania wystawione tokeny lub podczas negocjowania lub Odnawianie tokenów kontekstów zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="0c958-129">Specifying short lifetimes, on the order of 30 seconds or less for issued tokens or security context tokens, may result in negotiation time-outs or other exceptions being thrown by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients when requesting issued tokens or when negotiating or renewing security context tokens.</span></span>  
  
## <a name="issued-tokens-and-inclusionmode"></a><span data-ttu-id="0c958-130">Wystawione tokeny i InclusionMode</span><span class="sxs-lookup"><span data-stu-id="0c958-130">Issued Tokens and InclusionMode</span></span>  
 <span data-ttu-id="0c958-131">Określa, czy wystawionego tokenu jest serializowany w wiadomości wysłanych z klienta do punktu końcowego federacyjnych lub nie jest kontrolowany przez ustawienie <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InclusionMode%2A> właściwość <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters> klasy.</span><span class="sxs-lookup"><span data-stu-id="0c958-131">Whether an issued token is serialized in a message sent from a client to a federated endpoint or not is controlled by setting the <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InclusionMode%2A> property of the <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters> class.</span></span> <span data-ttu-id="0c958-132">Ta właściwość może należeć do jednej z <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> wartości wyliczenia, ale nie jest przydatne w scenariuszach obejmujących Federację najbardziej.</span><span class="sxs-lookup"><span data-stu-id="0c958-132">This property can be set to one of the <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> enumeration values, but it is not useful in most federated scenarios.</span></span> <span data-ttu-id="0c958-133">`SecurityTokenInclusionMode.Never` i `SecurityTokenInclusionMode.AlwaysToInitiator` wartości spowoduje to klientowi wysłanie odwołania do tokenu wystawiony przez usługę tokenu zabezpieczającego do jednostki uzależnionej.</span><span class="sxs-lookup"><span data-stu-id="0c958-133">The `SecurityTokenInclusionMode.Never` and `SecurityTokenInclusionMode.AlwaysToInitiator` values cause the client to send a reference to the token issued by the security token service to the relying party.</span></span> <span data-ttu-id="0c958-134">O ile uzależnionej posiada kopię wystawionego tokenu uwierzytelniania zakończy się niepowodzeniem, ponieważ nie można rozpoznać odwołania do tokenu.</span><span class="sxs-lookup"><span data-stu-id="0c958-134">Unless the relying party possesses a copy of the issued token, authentication will fail because the token reference is not resolvable.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c958-135">traktuje `SecurityTokenInclusionMode.Once` jako równoważne `SecurityTokenInclusionMode.AlwaysToRecipient`.</span><span class="sxs-lookup"><span data-stu-id="0c958-135"> treats `SecurityTokenInclusionMode.Once` as equivalent to `SecurityTokenInclusionMode.AlwaysToRecipient`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c958-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0c958-136">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>  
 [<span data-ttu-id="0c958-137">Porady: Tworzenie klienta federacyjnego</span><span class="sxs-lookup"><span data-stu-id="0c958-137">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="0c958-138">Porady: Konfigurowanie poświadczeń usługi federacyjnej</span><span class="sxs-lookup"><span data-stu-id="0c958-138">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="0c958-139">Porady: tworzenie WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="0c958-139">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)