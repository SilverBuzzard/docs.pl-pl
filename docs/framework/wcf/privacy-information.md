---
title: "Informacje o prywatności dotyczące architektury WCF (Windows Communication Foundation)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
caps.latest.revision: "34"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 53fc4be67fd3f6a7b2b8c914c11fb6540b28c199
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="1ff00-102">Informacje o prywatności dotyczące architektury WCF (Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="1ff00-102">Windows Communication Foundation Privacy Information</span></span>
<span data-ttu-id="1ff00-103">Firma Microsoft dba o ochronę prywatności użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-103">Microsoft is committed to protecting end-users' privacy.</span></span> <span data-ttu-id="1ff00-104">Podczas budowania aplikacji przy użyciu [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], wersja 3.0, aplikacja może mieć wpływ na prywatność użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-104">When you build an application using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], version 3.0, your application may impact your end-users' privacy.</span></span> <span data-ttu-id="1ff00-105">Na przykład aplikacja jawnie może zbierać informacje kontaktowe użytkownika lub może zażądać, lub wysłać informacje przez Internet do witryny sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1ff00-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="1ff00-106">Jeśli technologii firmy Microsoft możesz osadzić w aplikacji, technologia ta może być własną zachowanie, które mogą mieć wpływ na prywatność.</span><span class="sxs-lookup"><span data-stu-id="1ff00-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-107">nie wysyła żadnych informacji do firmy Microsoft z aplikacji, chyba że użytkownik lub użytkownik końcowy wybrać do wysyłania do nas.</span><span class="sxs-lookup"><span data-stu-id="1ff00-107"> does not send any information to Microsoft from your application unless you or the end-user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="1ff00-108">Usługi WCF w Brief</span><span class="sxs-lookup"><span data-stu-id="1ff00-108">WCF in Brief</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-109">rozproszone framework komunikatów używa programu Microsoft .NET Framework, która umożliwia deweloperom tworzenie aplikacji rozproszonych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-109"> is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="1ff00-110">Komunikaty przekazywane między dwiema aplikacjami zawierają informacje nagłówek i treść.</span><span class="sxs-lookup"><span data-stu-id="1ff00-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="1ff00-111">Nagłówki może zawierać rozsyłania wiadomości, informacje o zabezpieczeniach transakcji i dłużej w zależności od usługi używane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="1ff00-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="1ff00-112">Komunikaty są zwykle domyślnie szyfrowane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="1ff00-113">Jedynym wyjątkiem jest przy użyciu `BasicHttpBinding`, który został zaprojektowany do użytku z usługami sieci Web nie jest zabezpieczony, starszej wersji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="1ff00-114">Projektant aplikacji jest odpowiedzialny za ostatecznego projektu.</span><span class="sxs-lookup"><span data-stu-id="1ff00-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="1ff00-115">W treści protokołu SOAP wiadomości dane specyficzne dla aplikacji; Jednak te dane, takie jak zdefiniowane przez aplikację informacje osobiste, mogą być chronione przy użyciu [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] funkcje szyfrowania i poufności.</span><span class="sxs-lookup"><span data-stu-id="1ff00-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] encryption or confidentiality features.</span></span> <span data-ttu-id="1ff00-116">W poniższych sekcjach opisano funkcje, które mogą mieć wpływ na prywatność.</span><span class="sxs-lookup"><span data-stu-id="1ff00-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="1ff00-117">Obsługa wiadomości</span><span class="sxs-lookup"><span data-stu-id="1ff00-117">Messaging</span></span>  
 <span data-ttu-id="1ff00-118">Każdy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] wiadomość zawiera nagłówek adres, który określa lokalizację docelową wiadomości i gdzie odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="1ff00-118">Each [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="1ff00-119">Składnik adres adresu punktu końcowego jest zasobów identyfikator URI (Uniform), który identyfikuje punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="1ff00-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="1ff00-120">Adres może być adresu sieciowego lub adres logiczny.</span><span class="sxs-lookup"><span data-stu-id="1ff00-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="1ff00-121">Adres może zawierać nazwy komputera (nazwa hosta, pełna nazwa domeny) i adres IP.</span><span class="sxs-lookup"><span data-stu-id="1ff00-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="1ff00-122">Adres punktu końcowego może również zawierać unikatowy identyfikator globalny (GUID) lub kolekcja identyfikatorów GUID adresowania tymczasowych używany do wykrycia każdy adres.</span><span class="sxs-lookup"><span data-stu-id="1ff00-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="1ff00-123">Każdy komunikat zawiera identyfikator wiadomości, który jest identyfikatorem GUID.</span><span class="sxs-lookup"><span data-stu-id="1ff00-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="1ff00-124">Ta funkcja jest zgodna standardowego wzorca WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="1ff00-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="1ff00-125">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Warstwa obsługi wiadomości nie zapisuje żadnych informacji osobistych na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="1ff00-125">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="1ff00-126">Jednak go może propagowania informacji osobistych na poziomie sieci Jeśli dewelopera usługi utworzył to usługa, która udostępnia takie informacje (na przykład za pomocą nazwisko osoby w nazwie punktu końcowego, lub w tym informacje osobiste w sieci Web punktu końcowego Services Description Language, ale nie wymaga klientów do używania protokołu https można uzyskać dostępu do WSDL).</span><span class="sxs-lookup"><span data-stu-id="1ff00-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="1ff00-127">Ponadto, gdy działa dewelopera [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) narzędzie względem punktu końcowego, który opisuje informacje osobiste, dane wyjściowe narzędzia mogą zawierać te informacje i są zapisywane w pliku docelowym lokalny dysk twardy.</span><span class="sxs-lookup"><span data-stu-id="1ff00-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="1ff00-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="1ff00-128">Hosting</span></span>  
 <span data-ttu-id="1ff00-129">Funkcję hostingu w [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] umożliwia aplikacjom można uruchomić na żądanie lub włączyć Udostępnianie portów między wieloma aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="1ff00-129">The hosting feature in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="1ff00-130">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Aplikacji może być hostowana w Internet Information Services (IIS), podobny do [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ff00-130">An [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application can be hosted in Internet Information Services (IIS), similar to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="1ff00-131">Hosting nie ujawnia żadnych określonych informacji w sieci i nie przechowuje danych na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="1ff00-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="1ff00-132">Zabezpieczenia komunikatów</span><span class="sxs-lookup"><span data-stu-id="1ff00-132">Message Security</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-133">funkcja zabezpieczenia oferuje funkcje zabezpieczeń dla aplikacji do obsługi wiadomości.</span><span class="sxs-lookup"><span data-stu-id="1ff00-133"> security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="1ff00-134">Dostępne funkcje zabezpieczeń obejmują uwierzytelniania i autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="1ff00-135">Uwierzytelnianie jest wykonywane przez przekazanie poświadczeń między klientami i usługami.</span><span class="sxs-lookup"><span data-stu-id="1ff00-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="1ff00-136">Uwierzytelniania mogą być przez zabezpieczenia na poziomie transportu lub za pośrednictwem protokołu SOAP wiadomości poziomu zabezpieczeń, w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1ff00-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
-   <span data-ttu-id="1ff00-137">W ramach zabezpieczeń komunikatów SOAP uwierzytelnianie jest przeprowadzane za pomocą poświadczeń, takie jak nazwa użytkownika/hasła, certyfikaty X.509 biletów Kerberos i tokeny SAML, które mogą zawierać informacje osobiste, w zależności od wystawcy.</span><span class="sxs-lookup"><span data-stu-id="1ff00-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
-   <span data-ttu-id="1ff00-138">Za pomocą zabezpieczeń transportu, uwierzytelnianie odbywa się za pośrednictwem tradycyjnych transportu mechanizmów uwierzytelniania, takich jak schematy uwierzytelniania HTTP (Basic, Digest, Negotiate, zintegrowanej autoryzacji systemu Windows, NTLM, None i anonimowe) i uwierzytelniania formularzy.</span><span class="sxs-lookup"><span data-stu-id="1ff00-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="1ff00-139">Uwierzytelnianie może spowodować bezpiecznej sesji między komunikacji punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="1ff00-140">Sesja jest identyfikowany przez identyfikator GUID, który jest ważny przez czas ich istnienia sesji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="1ff00-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="1ff00-141">W poniższej tabeli pokazano, co jest zachowywane i gdzie.</span><span class="sxs-lookup"><span data-stu-id="1ff00-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="1ff00-142">Dane</span><span class="sxs-lookup"><span data-stu-id="1ff00-142">Data</span></span>|<span data-ttu-id="1ff00-143">Magazyn</span><span class="sxs-lookup"><span data-stu-id="1ff00-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="1ff00-144">Poświadczenia prezentacji, takie jak nazwa użytkownika, certyfikaty X.509, tokeny protokołu Kerberos i odwołania do poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="1ff00-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="1ff00-145">Standardowy system Windows poświadczeń mechanizmów zarządzania, takich jak magazynu certyfikatów systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="1ff00-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="1ff00-146">Członkostwo informacje o użytkowniku, takie jak nazwy użytkowników i hasła.</span><span class="sxs-lookup"><span data-stu-id="1ff00-146">User membership information, such as usernames and passwords.</span></span>|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]<span data-ttu-id="1ff00-147">dostawcy członkostwa.</span><span class="sxs-lookup"><span data-stu-id="1ff00-147"> membership providers.</span></span>|  
|<span data-ttu-id="1ff00-148">Informacje dotyczące usługi używany do uwierzytelniania usługi dla klientów tożsamości.</span><span class="sxs-lookup"><span data-stu-id="1ff00-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="1ff00-149">Adres punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="1ff00-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="1ff00-150">Informacje o wywołującym.</span><span class="sxs-lookup"><span data-stu-id="1ff00-150">Caller information.</span></span>|<span data-ttu-id="1ff00-151">Dzienniki inspekcji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="1ff00-152">Inspekcja</span><span class="sxs-lookup"><span data-stu-id="1ff00-152">Auditing</span></span>  
 <span data-ttu-id="1ff00-153">Inspekcja rejestruje sukces i niepowodzenie zdarzeń uwierzytelniania i autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="1ff00-154">Rekordy inspekcji zawierają następujące dane: z identyfikatora URI, identyfikator URI akcji i identyfikator obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="1ff00-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="1ff00-155">Inspekcja również są rejestrowane podczas administrator Modyfikuje konfigurację rejestrowanie komunikatów (Włączanie on lub off), ponieważ rejestrowanie komunikatów mogą rejestrować dane specyficzne dla aplikacji w nagłówkach i treści.</span><span class="sxs-lookup"><span data-stu-id="1ff00-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="1ff00-156">Aby uzyskać [!INCLUDE[wxp](../../../includes/wxp-md.md)], rekord jest rejestrowane w dzienniku zdarzeń aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-156">For [!INCLUDE[wxp](../../../includes/wxp-md.md)], a record is logged in the application event log.</span></span> <span data-ttu-id="1ff00-157">Aby uzyskać [!INCLUDE[wv](../../../includes/wv-md.md)] i [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], rekord jest rejestrowane w dzienniku zdarzeń zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="1ff00-157">For [!INCLUDE[wv](../../../includes/wv-md.md)] and [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="1ff00-158">Transakcje</span><span class="sxs-lookup"><span data-stu-id="1ff00-158">Transactions</span></span>  
 <span data-ttu-id="1ff00-159">Funkcja transakcji zapewnia transakcyjnych usług [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-159">The transactions feature provides transactional services to a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span>  
  
 <span data-ttu-id="1ff00-160">Nagłówki transakcji używanych w propagacji transakcji mogą zawierać identyfikatorów transakcji lub rejestracji identyfikatorów, które są identyfikatorami GUID.</span><span class="sxs-lookup"><span data-stu-id="1ff00-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="1ff00-161">Funkcja transakcji używa Menedżera transakcji koordynatora transakcji rozproszonych (MSDTC) (składnik systemu Windows) do zarządzania stanem transakcji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="1ff00-162">Domyślnie komunikacja między menedżerami transakcje są szyfrowane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="1ff00-163">Menedżerowie transakcji mogą rejestrować odwołania do punktu końcowego, identyfikatory transakcji i identyfikatory rejestracji w ramach stanu trwałego.</span><span class="sxs-lookup"><span data-stu-id="1ff00-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="1ff00-164">Okres istnienia tego stanu jest określana przez okres istnienia pliku dziennika Menedżera transakcji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="1ff00-165">Usługa MSDTC jest właścicielem i przechowuje ten dziennik.</span><span class="sxs-lookup"><span data-stu-id="1ff00-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="1ff00-166">Funkcja transakcji implementuje standardy koordynacji WS i protokołu WS-AT.</span><span class="sxs-lookup"><span data-stu-id="1ff00-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="1ff00-167">Niezawodne sesje</span><span class="sxs-lookup"><span data-stu-id="1ff00-167">Reliable Sessions</span></span>  
 <span data-ttu-id="1ff00-168">Niezawodne sesje w [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] przesyłanie komunikatów, gdy występują błędy transportu lub pośrednika.</span><span class="sxs-lookup"><span data-stu-id="1ff00-168">Reliable sessions in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="1ff00-169">Udostępniają one dokładnie — raz transferu wiadomości, nawet wtedy, gdy transportu źródłowego rozłącza (na przykład połączenie TCP w sieci bezprzewodowej) lub utraci wiadomości (serwer proxy HTTP porzucenie komunikat wychodzące lub przychodzące).</span><span class="sxs-lookup"><span data-stu-id="1ff00-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="1ff00-170">Niezawodne sesje także odzyskać komunikat zmianę kolejności (co może się tak zdarzyć w przypadku wielu ścieżek routing), zachowując kolejności, w jakiej zostały wysłane wiadomości.</span><span class="sxs-lookup"><span data-stu-id="1ff00-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="1ff00-171">Niezawodne sesje są implementowane za pomocą protokołu WS-ReliableMessaging (WS-RM).</span><span class="sxs-lookup"><span data-stu-id="1ff00-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="1ff00-172">Dodaj one nagłówków protokołu WS-RM, zawierające informacje sesji, który jest używany do identyfikowania komunikatów wszystkich skojarzonych z określonym niezawodnej sesji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="1ff00-173">Każdej sesji protokołu WS-RM ma identyfikator, który jest identyfikatorem GUID.</span><span class="sxs-lookup"><span data-stu-id="1ff00-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="1ff00-174">Żadne informacje osobiste nie są przechowywane na komputerze użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="1ff00-174">No personal information is retained on the end-user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="1ff00-175">Kanały w kolejce</span><span class="sxs-lookup"><span data-stu-id="1ff00-175">Queued Channels</span></span>  
 <span data-ttu-id="1ff00-176">Kolejki przechowywania komunikatów z aplikacja wysyłająca imieniu aplikację i później przekazywanie tych wiadomości do aplikacji odbierającej.</span><span class="sxs-lookup"><span data-stu-id="1ff00-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="1ff00-177">One zapewnić transferu wiadomości z aplikacji wysyłającej aplikacje odbierające, na przykład aplikacja odbierająca jest przejściowy.</span><span class="sxs-lookup"><span data-stu-id="1ff00-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-178">zapewnia obsługę dla usługi kolejkowania wiadomości przy użyciu usługi kolejkowania wiadomości firmy Microsoft (MSMQ) do ich przenoszenia.</span><span class="sxs-lookup"><span data-stu-id="1ff00-178"> provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="1ff00-179">Funkcja kanałów w kolejce nie dodaje nagłówki na wiadomość.</span><span class="sxs-lookup"><span data-stu-id="1ff00-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="1ff00-180">Zamiast tego tworzy komunikatów usługi kolejkowania komunikatów z odpowiedniego zbioru właściwości komunikatów usługi kolejkowania komunikatów i wywołuje metody kolejkowania put wiadomości w kolejce usługi kolejkowania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="1ff00-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="1ff00-181">Usługa kolejkowania komunikatów jest opcjonalnym składnikiem, który jest dostarczany z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="1ff00-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="1ff00-182">Nie informacje są przechowywane na komputerze użytkownika końcowego przez funkcję umieszczonych w kolejce kanałów, ponieważ używa usługi kolejkowania komunikatów jako kolejkowania infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="1ff00-182">No information is retained on the end-user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="1ff00-183">Integracja modelu COM+</span><span class="sxs-lookup"><span data-stu-id="1ff00-183">COM+ Integration</span></span>  
 <span data-ttu-id="1ff00-184">Ta funkcja jest zawijana istniejące funkcje COM i COM + do tworzenia usług, które są zgodne z [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usług.</span><span class="sxs-lookup"><span data-stu-id="1ff00-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="1ff00-185">Ta funkcja nie korzysta z określonych nagłówków i nie zachowuje danych na komputerze użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="1ff00-185">This feature does not use specific headers and it does not retain data on the end-user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="1ff00-186">Moniker usługi COM</span><span class="sxs-lookup"><span data-stu-id="1ff00-186">COM Service Moniker</span></span>  
 <span data-ttu-id="1ff00-187">Zapewnia to niezarządzany otoki do standardowego [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klienta.</span><span class="sxs-lookup"><span data-stu-id="1ff00-187">This provides an unmanaged wrapper to a standard [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span> <span data-ttu-id="1ff00-188">Ta funkcja nie ma określonego nagłówki przesyłania ani jest utrwalenia danych na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="1ff00-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="1ff00-189">Kanał elementu równorzędnego</span><span class="sxs-lookup"><span data-stu-id="1ff00-189">Peer Channel</span></span>  
 <span data-ttu-id="1ff00-190">Kanał elementu równorzędnego umożliwia programowanie wielopartyjnej aplikacji przy użyciu [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ff00-190">A peer channel enables development of multiparty applications using [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="1ff00-191">Wiadomości wielopartyjnej występuje w kontekście siatki.</span><span class="sxs-lookup"><span data-stu-id="1ff00-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="1ff00-192">Siatki są identyfikowane przez nazwę, która może dołączać węzłów.</span><span class="sxs-lookup"><span data-stu-id="1ff00-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="1ff00-193">Każdy węzeł w kanału równorzędnego tworzy odbiornika TCP w porcie określone przez użytkownika i ustanawia połączenie z innych węzłach w sieci w celu zapewnienia odporności.</span><span class="sxs-lookup"><span data-stu-id="1ff00-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="1ff00-194">Aby połączyć inne węzły w siatce, węzły wymiany niektórych danych, w tym adres odbiornika i adresów IP na komputerze, na innych węzłach w sieci.</span><span class="sxs-lookup"><span data-stu-id="1ff00-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="1ff00-195">Komunikaty wysyłane wokół w siatce może zawierać zabezpieczeń informacji dotyczących nadawcy, aby uniknąć fałszowania wiadomości i naruszeniu.</span><span class="sxs-lookup"><span data-stu-id="1ff00-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="1ff00-196">Żadne informacje osobiste nie są przechowywane na komputerze użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="1ff00-196">No personal information is stored on the end-user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="1ff00-197">Środowisko pracy specjalistów IT</span><span class="sxs-lookup"><span data-stu-id="1ff00-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="1ff00-198">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="1ff00-198">Tracing</span></span>  
 <span data-ttu-id="1ff00-199">Funkcja diagnostyki [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] infrastruktury rejestruje komunikaty, które przechodzą przez warstwy modelu transportu i usługi oraz działania i zdarzeń związanych z tych wiadomości.</span><span class="sxs-lookup"><span data-stu-id="1ff00-199">The diagnostics feature of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="1ff00-200">Ta funkcja jest domyślnie wyłączona.</span><span class="sxs-lookup"><span data-stu-id="1ff00-200">This feature is turned off by default.</span></span> <span data-ttu-id="1ff00-201">Jest włączone, za pomocą pliku konfiguracji aplikacji i zachowanie śledzenia może zostać zmodyfikowany za pomocą [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] dostawcy WMI w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="1ff00-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] WMI provider at run time.</span></span> <span data-ttu-id="1ff00-202">Po włączeniu Infrastruktura śledzenia emituje śledzenia diagnostycznego, zawierający wiadomości, działań i odbiorników skonfigurowanych przetwarzania zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="1ff00-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="1ff00-203">Format i lokalizacja danych wyjściowych zależą od opcji konfiguracji odbiornika administratora, ale jest zwykle sformatowanym plikiem XML.</span><span class="sxs-lookup"><span data-stu-id="1ff00-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="1ff00-204">Administrator jest odpowiedzialny za ustawienie listy kontroli dostępu (ACL) dla plików śledzenia.</span><span class="sxs-lookup"><span data-stu-id="1ff00-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="1ff00-205">W szczególności obsługiwany przez System aktywacji systemu Windows (WAS), administrator powinien upewnij się, że pliki nie są obsługiwane z katalogu publiczny wirtualnego katalogu głównego, jeśli nie jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="1ff00-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="1ff00-206">Istnieją dwa typy śledzenie: rejestrowanie komunikatów i modelu usługi diagnostyczne śledzenia, opisane w poniższej sekcji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="1ff00-207">Każdy typ jest skonfigurowana za pośrednictwem źródła śledzenia: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> i <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="1ff00-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="1ff00-208">Oba te źródła śledzenia rejestrowania przechwytywania danych, które są lokalne dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="1ff00-209">Rejestrowanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="1ff00-209">Message Logging</span></span>  
 <span data-ttu-id="1ff00-210">Rejestrowanie źródła śledzenia komunikatów (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) umożliwia administratorom komunikaty dziennika przepływające za pośrednictwem systemu.</span><span class="sxs-lookup"><span data-stu-id="1ff00-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="1ff00-211">Za pomocą konfiguracji użytkownik może zadecydować o dziennika całego wiadomości lub tylko nagłówki komunikatu, czy mają być rejestrowane w modelu warstwy transportu i/lub usługi i czy mają być źle sformułowane wiadomości.</span><span class="sxs-lookup"><span data-stu-id="1ff00-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="1ff00-212">Ponadto użytkownik może konfigurować filtrowania do ograniczenia, które komunikaty są rejestrowane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="1ff00-213">Domyślnie rejestrowanie komunikatów jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="1ff00-213">By default, message logging is disabled.</span></span> <span data-ttu-id="1ff00-214">Administratora komputera lokalnego uniemożliwi włączanie komunikat logowania administratora poziomie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="1ff00-215">Rejestrowanie komunikatów zaszyfrowane i odszyfrowane</span><span class="sxs-lookup"><span data-stu-id="1ff00-215">Encrypted and Decrypted Message Logging</span></span>  
 <span data-ttu-id="1ff00-216">Komunikaty są rejestrowane, szyfrowane lub odszyfrować, zgodnie z opisem w następujących warunkach.</span><span class="sxs-lookup"><span data-stu-id="1ff00-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="1ff00-217">Rejestrowanie transportu</span><span class="sxs-lookup"><span data-stu-id="1ff00-217">Transport Logging</span></span>  
 <span data-ttu-id="1ff00-218">Rejestruje komunikaty odebranych i wysłanych na poziomie transportu.</span><span class="sxs-lookup"><span data-stu-id="1ff00-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="1ff00-219">Te komunikaty zawierają wszystkie nagłówki i może być zaszyfrowany przed wysłaniem przesyłania i podczas odbierane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="1ff00-220">W przypadku wiadomości są szyfrowane przed wysłaniem przesyłania i po odebraniu, są rejestrowane również szyfrowane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="1ff00-221">Wyjątek jest gdy protokół zabezpieczeń jest używana (https): są następnie rejestrowane odszyfrować przed wysłaniem i po nich odbierane, nawet jeśli są one zaszyfrowane w trakcie przesyłania.</span><span class="sxs-lookup"><span data-stu-id="1ff00-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="1ff00-222">Usługa rejestrowania</span><span class="sxs-lookup"><span data-stu-id="1ff00-222">Service Logging</span></span>  
 <span data-ttu-id="1ff00-223">Rejestruje komunikaty odebranych lub wysłanych na poziomie modelu usługi, po podczas przetwarzania nagłówka kanału, bezpośrednio przed i po wprowadzeniu kodu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1ff00-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="1ff00-224">Komunikaty zarejestrowane na tym poziomie są odszyfrowywane, nawet jeśli były zabezpieczone i zaszyfrowane w trakcie przesyłania.</span><span class="sxs-lookup"><span data-stu-id="1ff00-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="1ff00-225">Rejestrowanie komunikatów źle sformułowany</span><span class="sxs-lookup"><span data-stu-id="1ff00-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="1ff00-226">Dzienniki wiadomości, które [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] infrastruktury nie może zrozumieć lub przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="1ff00-226">Logs messages that the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="1ff00-227">Komunikaty są rejestrowane jako — to znaczy szyfrowane lub nie</span><span class="sxs-lookup"><span data-stu-id="1ff00-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="1ff00-228">Jeśli komunikaty są rejestrowane odszyfrować lub niezaszyfrowanej postaci domyślnie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usuwa kluczy zabezpieczeń i potencjalnie dane osobowe z komunikatów przed ich zalogowaniem.</span><span class="sxs-lookup"><span data-stu-id="1ff00-228">When messages are logged in decrypted or unencrypted form, by default [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="1ff00-229">Kolejne sekcje opisują, jakie informacje zostaną usunięte oraz kiedy.</span><span class="sxs-lookup"><span data-stu-id="1ff00-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="1ff00-230">Administrator maszyny i jednocześnie wdrażania aplikacji należy wykonać pewne akcje konfiguracji, aby zmienić domyślne zachowanie logowania kluczy i potencjalnie danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="1ff00-231">Informacje o usunięte z nagłówków komunikatu podczas logowania się odszyfrować niezaszyfrowane wiadomości</span><span class="sxs-lookup"><span data-stu-id="1ff00-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="1ff00-232">Jeśli komunikaty są rejestrowane w odszyfrować niezaszyfrowanej postaci kluczy zabezpieczeń i potencjalnie danych osobowych są usuwane domyślnie nagłówki komunikatów i treści wiadomości, zanim są rejestrowane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="1ff00-233">Na poniższej liście przedstawiono co [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] uwzględnia kluczy i potencjalnie danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-233">The following list shows what [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="1ff00-234">Klucze, które zostały usunięte:</span><span class="sxs-lookup"><span data-stu-id="1ff00-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="1ff00-235">\-Xmlns:wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" i xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"</span><span class="sxs-lookup"><span data-stu-id="1ff00-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="1ff00-236">Wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="1ff00-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="1ff00-237">Wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="1ff00-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="1ff00-238">\-Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" i xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="1ff00-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="1ff00-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="1ff00-239">wsse:Password</span></span>  
  
 <span data-ttu-id="1ff00-240">wsse:nonce</span><span class="sxs-lookup"><span data-stu-id="1ff00-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="1ff00-241">Potencjalnie osobiste informacje zostaną usunięte:</span><span class="sxs-lookup"><span data-stu-id="1ff00-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="1ff00-242">\-Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" i xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="1ff00-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="1ff00-243">wsse:username</span><span class="sxs-lookup"><span data-stu-id="1ff00-243">wsse:Username</span></span>  
  
 <span data-ttu-id="1ff00-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="1ff00-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="1ff00-245">\-Dla xmlns:saml = "urn: oasis: nazwy: tc: SAML:1.0:assertion" są usuwane elementy pogrubione (poniżej):</span><span class="sxs-lookup"><span data-stu-id="1ff00-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="1ff00-246">\<Potwierdzenia</span><span class="sxs-lookup"><span data-stu-id="1ff00-246">\<Assertion</span></span>  
  
 <span data-ttu-id="1ff00-247">MajorVersion = "1"</span><span class="sxs-lookup"><span data-stu-id="1ff00-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="1ff00-248">MinorVersion = "1"</span><span class="sxs-lookup"><span data-stu-id="1ff00-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="1ff00-249">Identyfikator potwierdzenia = "[identyfikator]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="1ff00-250">Wystawca = "[parametry]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="1ff00-251">IssueInstant = "[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="1ff00-252">\<Warunki nie wcześniej niż = "[dateTime]" NotOnOrAfter = "[dateTime]" ></span><span class="sxs-lookup"><span data-stu-id="1ff00-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span></span>  
  
 <span data-ttu-id="1ff00-253">\<AudienceRestrictionCondition ></span><span class="sxs-lookup"><span data-stu-id="1ff00-253">\<AudienceRestrictionCondition></span></span>  
  
 <span data-ttu-id="1ff00-254">\<Grupy odbiorców > [identyfikator uri]\</Audience > +</span><span class="sxs-lookup"><span data-stu-id="1ff00-254">\<Audience>[uri]\</Audience>+</span></span>  
  
 <span data-ttu-id="1ff00-255">\</ AudienceRestrictionCondition > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-255">\</AudienceRestrictionCondition>*</span></span>  
  
 <span data-ttu-id="1ff00-256">\<DoNotCacheCondition / > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-256">\<DoNotCacheCondition />*</span></span>  
  
 <span data-ttu-id="1ff00-257"><\!--abstrakcyjnej typu podstawowego</span><span class="sxs-lookup"><span data-stu-id="1ff00-257"><\!-- abstract base type</span></span>  
  
 <span data-ttu-id="1ff00-258">\<Warunek / > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-258">\<Condition />*</span></span>  
  
 -->  
  
 <span data-ttu-id="1ff00-259">\</ Warunki >?</span><span class="sxs-lookup"><span data-stu-id="1ff00-259">\</Conditions>?</span></span>  
  
 <span data-ttu-id="1ff00-260">\<Porady ></span><span class="sxs-lookup"><span data-stu-id="1ff00-260">\<Advice></span></span>  
  
 <span data-ttu-id="1ff00-261">\<AssertionIDReference > [identyfikator]\</AssertionIDReference > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-261">\<AssertionIDReference>[ID]\</AssertionIDReference>*</span></span>  
  
 <span data-ttu-id="1ff00-262">\<Potwierdzenie > [potwierdzenie]\</Assertion > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-262">\<Assertion>[assertion]\</Assertion>*</span></span>  
  
 <span data-ttu-id="1ff00-263">[any] *</span><span class="sxs-lookup"><span data-stu-id="1ff00-263">[any]*</span></span>  
  
 <span data-ttu-id="1ff00-264">\</ Porady >?</span><span class="sxs-lookup"><span data-stu-id="1ff00-264">\</Advice>?</span></span>  
  
 <span data-ttu-id="1ff00-265"><\!--Abstrakcyjnych typów podstawowych</span><span class="sxs-lookup"><span data-stu-id="1ff00-265"><\!-- Abstract base types</span></span>  
  
 <span data-ttu-id="1ff00-266">\<Instrukcja / > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-266">\<Statement />*</span></span>  
  
 <span data-ttu-id="1ff00-267">\<SubjectStatement ></span><span class="sxs-lookup"><span data-stu-id="1ff00-267">\<SubjectStatement></span></span>  
  
 <span data-ttu-id="1ff00-268">\<Temat ></span><span class="sxs-lookup"><span data-stu-id="1ff00-268">\<Subject></span></span>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 <span data-ttu-id="1ff00-269">\<SubjectConfirmation ></span><span class="sxs-lookup"><span data-stu-id="1ff00-269">\<SubjectConfirmation></span></span>  
  
 <span data-ttu-id="1ff00-270">\<ConfirmationMethod > [anyUri]\</ConfirmationMethod > +</span><span class="sxs-lookup"><span data-stu-id="1ff00-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="1ff00-271">\<SubjectConfirmationData > [any]\</SubjectConfirmationData >?</span><span class="sxs-lookup"><span data-stu-id="1ff00-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="1ff00-272">\<DS:KeyInfo >... \</ds:KeyInfo >?</span><span class="sxs-lookup"><span data-stu-id="1ff00-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="1ff00-273">\</ SubjectConfirmation >?</span><span class="sxs-lookup"><span data-stu-id="1ff00-273">\</SubjectConfirmation>?</span></span>  
  
 <span data-ttu-id="1ff00-274">\</ Temat ></span><span class="sxs-lookup"><span data-stu-id="1ff00-274">\</Subject></span></span>  
  
 <span data-ttu-id="1ff00-275">\</ SubjectStatement > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-275">\</SubjectStatement>*</span></span>  
  
 -->  
  
 <span data-ttu-id="1ff00-276">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="1ff00-276">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="1ff00-277">AuthenticationMethod = "[identyfikator uri]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-277">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="1ff00-278">AuthenticationInstant = "[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-278">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="1ff00-279">[Podmiotu]</span><span class="sxs-lookup"><span data-stu-id="1ff00-279">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="1ff00-280">< AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="1ff00-280"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="1ff00-281">Atrybut AuthorityKind = "[QName]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-281">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="1ff00-282">Lokalizacja = "[identyfikator uri]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-282">Location="[uri]"</span></span>  
  
 <span data-ttu-id="1ff00-283">Powiązanie = "[identyfikator uri]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-283">Binding="[uri]"</span></span>  
  
 />*  
  
 <span data-ttu-id="1ff00-284">\</ AuthenticationStatement > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-284">\</AuthenticationStatement>*</span></span>  
  
 <span data-ttu-id="1ff00-285">\<AttributeStatement ></span><span class="sxs-lookup"><span data-stu-id="1ff00-285">\<AttributeStatement></span></span>  
  
 <span data-ttu-id="1ff00-286">[Podmiotu]</span><span class="sxs-lookup"><span data-stu-id="1ff00-286">[Subject]</span></span>  
  
 <span data-ttu-id="1ff00-287">\<Atrybut</span><span class="sxs-lookup"><span data-stu-id="1ff00-287">\<Attribute</span></span>  
  
 <span data-ttu-id="1ff00-288">AttributeName = "[parametry]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-288">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="1ff00-289">AttributeNamespace = "[identyfikator uri]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-289">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 <span data-ttu-id="1ff00-290">\</ Atrybut > +</span><span class="sxs-lookup"><span data-stu-id="1ff00-290">\</Attribute>+</span></span>  
  
 <span data-ttu-id="1ff00-291">\</ AttributeStatement > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-291">\</AttributeStatement>*</span></span>  
  
 <span data-ttu-id="1ff00-292">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="1ff00-292">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="1ff00-293">Zasób = "[identyfikator uri]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-293">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="1ff00-294">Decyzja = "[zezwolenia &#124; Odmów &#124; nieokreślony]"</span><span class="sxs-lookup"><span data-stu-id="1ff00-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="1ff00-295">[Podmiotu]</span><span class="sxs-lookup"><span data-stu-id="1ff00-295">[Subject]</span></span>  
  
 <span data-ttu-id="1ff00-296">\<Akcja Namespace = "[identyfikator uri]" > [parametry]\<Action > +</span><span class="sxs-lookup"><span data-stu-id="1ff00-296">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 <span data-ttu-id="1ff00-297">\<Dowód ></span><span class="sxs-lookup"><span data-stu-id="1ff00-297">\<Evidence></span></span>  
  
 <span data-ttu-id="1ff00-298">\<AssertionIDReference > [identyfikator]\</AssertionIDReference > +</span><span class="sxs-lookup"><span data-stu-id="1ff00-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="1ff00-299">\<Potwierdzenie > [potwierdzenie]\</Assertion > +</span><span class="sxs-lookup"><span data-stu-id="1ff00-299">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="1ff00-300">\</ Dowody >?</span><span class="sxs-lookup"><span data-stu-id="1ff00-300">\</Evidence>?</span></span>  
  
 <span data-ttu-id="1ff00-301">\</ AuthorizationDecisionStatement > *</span><span class="sxs-lookup"><span data-stu-id="1ff00-301">\</AuthorizationDecisionStatement>*</span></span>  
  
 <span data-ttu-id="1ff00-302">\</ Potwierdzenie ></span><span class="sxs-lookup"><span data-stu-id="1ff00-302">\</Assertion></span></span>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="1ff00-303">Informacje o usuwane z treści wiadomości, gdy rejestrowanie komunikatów odszyfrować niezaszyfrowanej</span><span class="sxs-lookup"><span data-stu-id="1ff00-303">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="1ff00-304">Jak opisano wcześniej, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usuwa klucze i znanych potencjalnie dane osobowe z nagłówki komunikatów zarejestrowane komunikaty odszyfrować niezaszyfrowane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-304">As previously described, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="1ff00-305">Ponadto [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usuwa klucze i znanych potencjalnie dane osobowe z treści wiadomości treści elementy i działania na poniższej liście, które opisują komunikaty zabezpieczeń związane z wymiany kluczy.</span><span class="sxs-lookup"><span data-stu-id="1ff00-305">In addition, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="1ff00-306">Dla następujących przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="1ff00-306">For the following namespaces:</span></span>  
  
 <span data-ttu-id="1ff00-307">xmlns:WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" i xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust" (na przykład, jeśli brak dostępnych akcji)</span><span class="sxs-lookup"><span data-stu-id="1ff00-307">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="1ff00-308">Informacje są usuwane z tych elementów treści, które obejmują wymiany kluczy:</span><span class="sxs-lookup"><span data-stu-id="1ff00-308">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="1ff00-309">Wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="1ff00-309">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="1ff00-310">Wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="1ff00-310">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="1ff00-311">Wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="1ff00-311">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="1ff00-312">Informacje są również usuwane dla każdego z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="1ff00-312">Information is also removed for each of the following Actions:</span></span>  
  
 <span data-ttu-id="1ff00-313">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue</span><span class="sxs-lookup"><span data-stu-id="1ff00-313">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue</span></span>  
  
 <span data-ttu-id="1ff00-314">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue</span><span class="sxs-lookup"><span data-stu-id="1ff00-314">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue</span></span>  
  
 <span data-ttu-id="1ff00-315">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/renew</span><span class="sxs-lookup"><span data-stu-id="1ff00-315">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew</span></span>  
  
 <span data-ttu-id="1ff00-316">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/renew</span><span class="sxs-lookup"><span data-stu-id="1ff00-316">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew</span></span>  
  
 <span data-ttu-id="1ff00-317">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel</span><span class="sxs-lookup"><span data-stu-id="1ff00-317">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel</span></span>  
  
 <span data-ttu-id="1ff00-318">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel</span><span class="sxs-lookup"><span data-stu-id="1ff00-318">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel</span></span>  
  
 <span data-ttu-id="1ff00-319">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/validate</span><span class="sxs-lookup"><span data-stu-id="1ff00-319">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate</span></span>  
  
 <span data-ttu-id="1ff00-320">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/validate</span><span class="sxs-lookup"><span data-stu-id="1ff00-320">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate</span></span>  
  
 <span data-ttu-id="1ff00-321">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT</span><span class="sxs-lookup"><span data-stu-id="1ff00-321">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT</span></span>  
  
 <span data-ttu-id="1ff00-322">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT</span><span class="sxs-lookup"><span data-stu-id="1ff00-322">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT</span></span>  
  
 <span data-ttu-id="1ff00-323">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend</span><span class="sxs-lookup"><span data-stu-id="1ff00-323">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend</span></span>  
  
 <span data-ttu-id="1ff00-324">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend</span><span class="sxs-lookup"><span data-stu-id="1ff00-324">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend</span></span>  
  
 <span data-ttu-id="1ff00-325">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/renew</span><span class="sxs-lookup"><span data-stu-id="1ff00-325">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew</span></span>  
  
 <span data-ttu-id="1ff00-326">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/renew</span><span class="sxs-lookup"><span data-stu-id="1ff00-326">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew</span></span>  
  
 <span data-ttu-id="1ff00-327">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel</span><span class="sxs-lookup"><span data-stu-id="1ff00-327">http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel</span></span>  
  
 <span data-ttu-id="1ff00-328">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel</span><span class="sxs-lookup"><span data-stu-id="1ff00-328">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel</span></span>  
  
 <span data-ttu-id="1ff00-329">http://schemas.xmlsoap.org/ws/2004/04/Security/Trust/RST/SCT</span><span class="sxs-lookup"><span data-stu-id="1ff00-329">http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT</span></span>  
  
 <span data-ttu-id="1ff00-330">http://schemas.xmlsoap.org/ws/2004/04/Security/Trust/RSTR/SCT</span><span class="sxs-lookup"><span data-stu-id="1ff00-330">http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT</span></span>  
  
 <span data-ttu-id="1ff00-331">http://schemas.xmlsoap.org/ws/2004/04/Security/Trust/RST/SCT-Amend</span><span class="sxs-lookup"><span data-stu-id="1ff00-331">http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend</span></span>  
  
 <span data-ttu-id="1ff00-332">http://schemas.xmlsoap.org/ws/2004/04/Security/Trust/RSTR/SCT-Amend</span><span class="sxs-lookup"><span data-stu-id="1ff00-332">http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend</span></span>  
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="1ff00-333">Informacje nie zostaną usunięte z nagłówków specyficzne dla aplikacji i danych treści</span><span class="sxs-lookup"><span data-stu-id="1ff00-333">No Information Is Removed from Application-specific Headers and Body Data</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-334">nie śledzi informacje osobiste w nagłówkach specyficzne dla aplikacji (na przykład ciągi zapytań) lub treści danych (na przykład numer karty kredytowej).</span><span class="sxs-lookup"><span data-stu-id="1ff00-334"> does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="1ff00-335">Po włączeniu rejestrowania komunikatów informacje osobiste w nagłówkach specyficzne dla aplikacji i informacje mogą być widoczne w dziennikach.</span><span class="sxs-lookup"><span data-stu-id="1ff00-335">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="1ff00-336">Ponownie wdrażania aplikacji jest odpowiedzialny za ustawienie listy kontroli dostępu dla plików dziennika i konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-336">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="1ff00-337">Może on również wyłączenie rejestrowania, jeśli on nie chce, aby te informacje mają być wyświetlane lub może on filtrować te informacje z plików dziennika po jest rejestrowany.</span><span class="sxs-lookup"><span data-stu-id="1ff00-337">He also can turn off logging if he does not want this information to be visible, or he may filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="1ff00-338">Śledzenie modelu usług</span><span class="sxs-lookup"><span data-stu-id="1ff00-338">Service Model Tracing</span></span>  
 <span data-ttu-id="1ff00-339">Źródła śledzenia modelu usług (<xref:System.ServiceModel>) umożliwia śledzenie działań i zdarzenia związane z przetwarzania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="1ff00-339">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="1ff00-340">Ta funkcja korzysta z funkcji diagnostycznych .NET Framework z <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="1ff00-340">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="1ff00-341">Jak <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> właściwości, lokalizację i jego listy ACL są użytkownika — można skonfigurować za pomocą plików konfiguracji aplikacji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ff00-341">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="1ff00-342">Podobnie jak w przypadku rejestrowania komunikatów lokalizacja pliku jest zawsze konfigurowane gdy administrator włączy śledzenie; w związku z tym administrator kontroluje listy ACL.</span><span class="sxs-lookup"><span data-stu-id="1ff00-342">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="1ff00-343">Ślady zawierał nagłówków komunikatów, gdy komunikat jest w zakresie.</span><span class="sxs-lookup"><span data-stu-id="1ff00-343">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="1ff00-344">Te same zasady ukrywania potencjalnie osobowych w nagłówkach wiadomości w poprzedniej sekcji: dane osobowe wcześniej ustaloną jest usuwane domyślnie z nagłówków śladów.</span><span class="sxs-lookup"><span data-stu-id="1ff00-344">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="1ff00-345">Zarówno administrator maszyny i wdrażania aplikacji musi zmodyfikować konfigurację, aby można było zalogować potencjalnie danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-345">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="1ff00-346">Jednak osobiste informacje zawarte w nagłówkach specyficzne dla aplikacji są rejestrowane w śladów.</span><span class="sxs-lookup"><span data-stu-id="1ff00-346">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="1ff00-347">Narzędzia wdrażania aplikacji jest odpowiedzialny za ustawienie listy kontroli dostępu do plików konfiguracji i śledzenia.</span><span class="sxs-lookup"><span data-stu-id="1ff00-347">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="1ff00-348">On również wyłączyć śledzenie Jeśli on nie chce, aby te informacje mają być wyświetlane lub on można odfiltrować te informacje z plików śledzenia, po jest rejestrowany.</span><span class="sxs-lookup"><span data-stu-id="1ff00-348">He also can turn off tracing if he does not want this information to be visible, or he can filter out this information from the trace files after it is logged.</span></span>  
  
 <span data-ttu-id="1ff00-349">W ramach śledzenia ServiceModel unikatowe identyfikatory (nazywane identyfikatory aktywności i zazwyczaj identyfikator GUID) łączenie różnych działań jako wiadomości przez różne części infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="1ff00-349">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="1ff00-350">Obiekty nasłuchujące śledzenia niestandardowych</span><span class="sxs-lookup"><span data-stu-id="1ff00-350">Custom Trace Listeners</span></span>  
 <span data-ttu-id="1ff00-351">Dla obu komunikat rejestrowania i śledzenia można skonfigurować odbiornik śledzenia niestandardowego, który może wysyłać dane śledzenia i komunikaty umieszczonego w (na przykład do zdalnej bazy danych).</span><span class="sxs-lookup"><span data-stu-id="1ff00-351">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="1ff00-352">Narzędzia wdrażania aplikacji jest odpowiedzialny za konfigurowanie niestandardowych odbiorników lub umożliwienie użytkownikom to zrobić.</span><span class="sxs-lookup"><span data-stu-id="1ff00-352">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="1ff00-353">Odpowiada on też żadnych informacji osobistych widoczne w lokalizacji zdalnej i stosowania prawidłowo listy kontroli dostępu do tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-353">He is also responsible for any personal information exposed at the remote location, and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="1ff00-354">Inne funkcje dla specjalistów IT</span><span class="sxs-lookup"><span data-stu-id="1ff00-354">Other features for IT Professionals</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-355">ma dostawcę WMI, który ujawnia [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] informacje o konfiguracji infrastruktury za pomocą usługi WMI (dostarczane z systemem Windows).</span><span class="sxs-lookup"><span data-stu-id="1ff00-355"> has a WMI provider that exposes the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="1ff00-356">Domyślnie interfejs WMI są dostępne dla administratorów.</span><span class="sxs-lookup"><span data-stu-id="1ff00-356">By default, the WMI interface is available to administrators.</span></span>  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-357">Konfiguracja korzysta z mechanizmu konfiguracji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ff00-357"> configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="1ff00-358">Pliki konfiguracji są przechowywane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="1ff00-358">The configuration files are stored on the machine.</span></span> <span data-ttu-id="1ff00-359">Deweloper aplikacji i administrator utworzyć pliki konfiguracji i listy ACL dla każdego wymagania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-359">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="1ff00-360">Plik konfiguracji może zawierać adresy punktów końcowych i łącza do certyfikaty w magazynie certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="1ff00-360">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="1ff00-361">Certyfikaty mogą służyć do zapewnienia danych aplikacji, aby skonfigurować różne właściwości funkcje używane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="1ff00-361">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-362">używa również funkcje .NET Framework zrzutu procesu przez wywołanie metody <xref:System.Environment.FailFast%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="1ff00-362"> also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="1ff00-363">IT Pro Tools</span><span class="sxs-lookup"><span data-stu-id="1ff00-363">IT Pro Tools</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="1ff00-364">dostępne są także następujące narzędzia specjalistów IT, które są dostępne w zestawie Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="1ff00-364"> also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="1ff00-365">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="1ff00-365">SvcTraceViewer.exe</span></span>  
 <span data-ttu-id="1ff00-366">Wyświetla podgląd [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] pliki śledzenia.</span><span class="sxs-lookup"><span data-stu-id="1ff00-366">The viewer displays [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] trace files.</span></span> <span data-ttu-id="1ff00-367">Podgląd pokazuje, niezależnie od informacji znajduje się w dane śledzenia.</span><span class="sxs-lookup"><span data-stu-id="1ff00-367">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="1ff00-368">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="1ff00-368">SvcConfigEditor.exe</span></span>  
 <span data-ttu-id="1ff00-369">Edytor zezwala użytkownikowi na tworzenie i edytowanie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] plików konfiguracyjnych.</span><span class="sxs-lookup"><span data-stu-id="1ff00-369">The editor allows the user to create and edit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration files.</span></span> <span data-ttu-id="1ff00-370">Edytor pokazuje, niezależnie od informacje są przechowywane w plikach konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-370">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="1ff00-371">Tego samego zadania można osiągnąć za pomocą edytora tekstu.</span><span class="sxs-lookup"><span data-stu-id="1ff00-371">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodelreg"></a><span data-ttu-id="1ff00-372">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="1ff00-372">ServiceModel_Reg</span></span>  
 <span data-ttu-id="1ff00-373">To narzędzie umożliwia użytkownikom zarządzanie ServiceModel instaluje na komputerze.</span><span class="sxs-lookup"><span data-stu-id="1ff00-373">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="1ff00-374">Narzędzie wyświetla komunikaty o stanie w oknie konsoli, kiedy uruchamia i, w rezultacie mogą być wyświetlane informacje o konfiguracji [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] instalacji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-374">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="1ff00-375">WSATConfig.exe i WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="1ff00-375">WSATConfig.exe and WSATUI.dll</span></span>  
 <span data-ttu-id="1ff00-376">Te narzędzia umożliwiają specjalistów IT skonfigurować interoperacyjne Obsługa sieci WS-AtomicTransaction w [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ff00-376">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="1ff00-377">Narzędzia wyświetlania i Zezwalaj użytkownikowi na zmianę wartości najczęściej używane ustawienia protokołu WS-AtomicTransaction przechowywane w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="1ff00-377">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="1ff00-378">Kompleksowe funkcje</span><span class="sxs-lookup"><span data-stu-id="1ff00-378">Cross-cutting Features</span></span>  
 <span data-ttu-id="1ff00-379">Następujące funkcje są powiązane.</span><span class="sxs-lookup"><span data-stu-id="1ff00-379">The following features are cross-cutting.</span></span> <span data-ttu-id="1ff00-380">Oznacza to, że można je składa się z żadnym z powyższych funkcji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-380">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="1ff00-381">Struktura usługi</span><span class="sxs-lookup"><span data-stu-id="1ff00-381">Service Framework</span></span>  
 <span data-ttu-id="1ff00-382">Nagłówki może zawierać identyfikator wystąpienia, który jest identyfikatorem GUID, który kojarzy komunikat z wystąpienia klasy CLR.</span><span class="sxs-lookup"><span data-stu-id="1ff00-382">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="1ff00-383">Web Services Description Language (WSDL) zawiera definicję portu.</span><span class="sxs-lookup"><span data-stu-id="1ff00-383">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="1ff00-384">Każdy port ma adres punktu końcowego i powiązania, które reprezentuje usługi używane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="1ff00-384">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="1ff00-385">Udostępnianie WSDL można wyłączyć za pomocą konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1ff00-385">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="1ff00-386">Żadne informacje nie są przechowywane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="1ff00-386">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff00-387">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1ff00-387">See Also</span></span>  
 [<span data-ttu-id="1ff00-388">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1ff00-388">Windows Communication Foundation</span></span>](http://msdn.microsoft.com/en-us/fd327ade-0260-4c40-adbe-b74645ba3277)  
 [<span data-ttu-id="1ff00-389">Zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="1ff00-389">Security</span></span>](../../../docs/framework/wcf/feature-details/security.md)