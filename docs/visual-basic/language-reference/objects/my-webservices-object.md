---
title: "My.WebServices — Obiekt"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords: My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9f2c4017a1df8059f2cc57e7c30a96c474cfda0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="mywebservices-object"></a><span data-ttu-id="6b40a-102">My.WebServices — Obiekt</span><span class="sxs-lookup"><span data-stu-id="6b40a-102">My.WebServices Object</span></span>
<span data-ttu-id="6b40a-103">Udostępnia właściwości umożliwiające tworzenie i uzyskiwanie dostępu do jednego wystąpienia każdej usługi XML sieci Web odwołuje się do bieżącego projektu.</span><span class="sxs-lookup"><span data-stu-id="6b40a-103">Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b40a-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6b40a-104">Remarks</span></span>  
 <span data-ttu-id="6b40a-105">`My.WebServices` Obiektu zawiera wystąpienie poszczególnych usług sieci Web odwołuje się do bieżącego projektu.</span><span class="sxs-lookup"><span data-stu-id="6b40a-105">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="6b40a-106">Każde wystąpienie jest tworzone na żądanie.</span><span class="sxs-lookup"><span data-stu-id="6b40a-106">Each instance is instantiated on demand.</span></span> <span data-ttu-id="6b40a-107">Dostęp do tych usług sieci Web za pośrednictwem właściwości `My.WebServices` obiektu.</span><span class="sxs-lookup"><span data-stu-id="6b40a-107">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="6b40a-108">Nazwa właściwości jest taka sama jak nazwa usługi sieci Web, który uzyskuje dostęp do właściwości.</span><span class="sxs-lookup"><span data-stu-id="6b40a-108">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="6b40a-109">Każda klasa, która dziedziczy <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> to usługa sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6b40a-109">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span> <span data-ttu-id="6b40a-110">Informacje dotyczące dodawania usługi sieci Web do projektu, zobacz [podczas uzyskiwania dostępu do usługi sieci Web aplikacji](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="6b40a-110">For information about adding Web services to a project, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="6b40a-111">`My.WebServices` Obiekt udostępnia tylko usługi sieci Web skojarzony z bieżącego projektu.</span><span class="sxs-lookup"><span data-stu-id="6b40a-111">The `My.WebServices` object exposes only the Web services associated with the current project.</span></span> <span data-ttu-id="6b40a-112">Nie ma dostępu do usług sieci Web zadeklarowany w przywoływane biblioteki dll.</span><span class="sxs-lookup"><span data-stu-id="6b40a-112">It does not provide access to Web services declared in referenced DLLs.</span></span> <span data-ttu-id="6b40a-113">Aby uzyskać dostęp do usługi sieci Web, która udostępnia bibliotekę DLL, należy użyć kwalifikowaną nazwę usługi sieci Web w postaci *DllName*. *WebServiceName*.</span><span class="sxs-lookup"><span data-stu-id="6b40a-113">To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*.</span></span> <span data-ttu-id="6b40a-114">Aby uzyskać więcej informacji, zobacz [podczas uzyskiwania dostępu do usługi sieci Web aplikacji](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="6b40a-114">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="6b40a-115">Obiekt i jego właściwości nie są dostępne dla aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6b40a-115">The object and its properties are not available for Web applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6b40a-116">Właściwości</span><span class="sxs-lookup"><span data-stu-id="6b40a-116">Properties</span></span>  
 <span data-ttu-id="6b40a-117">Każda właściwość `My.WebServices` obiektu zapewnia dostęp do wystąpienia usługi sieci Web odwołuje się do bieżącego projektu.</span><span class="sxs-lookup"><span data-stu-id="6b40a-117">Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project.</span></span> <span data-ttu-id="6b40a-118">Nazwa właściwości jest taka sama jak nazwa usługi sieci Web, który uzyskuje dostęp do właściwości, a typ właściwości jest taki sam jak typ usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6b40a-118">The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b40a-119">W przypadku kolizję nazw, nazwa właściwości do uzyskiwania dostępu do usługi sieci Web jest *RootNamespace*_*Namespace*\_*ServiceName*.</span><span class="sxs-lookup"><span data-stu-id="6b40a-119">If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*.</span></span> <span data-ttu-id="6b40a-120">Rozważmy na przykład dwie usługi sieci Web o nazwie `Service1`.</span><span class="sxs-lookup"><span data-stu-id="6b40a-120">For example, consider two Web services named `Service1`.</span></span> <span data-ttu-id="6b40a-121">Jeśli jeden z tych usług znajduje się w głównej przestrzeni nazw `WindowsApplication1` i w przestrzeni nazw `Namespace1`, aby dostęp do tej usługi przy użyciu `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span><span class="sxs-lookup"><span data-stu-id="6b40a-121">If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span></span>  
  
 <span data-ttu-id="6b40a-122">Gdy użytkownik najpierw uzyskanie dostępu do `My.WebServices` właściwości obiektu tworzy nowe wystąpienie usługi sieci Web i zapisze go.</span><span class="sxs-lookup"><span data-stu-id="6b40a-122">When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it.</span></span> <span data-ttu-id="6b40a-123">Kolejne uzyskuje dostęp do tej właściwości zwrócił tego wystąpienia usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6b40a-123">Subsequent accesses of that property return that instance of the Web service.</span></span>  
  
 <span data-ttu-id="6b40a-124">Można usunąć usługi sieci Web, przypisując `Nothing` do właściwości tej usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6b40a-124">You can dispose of a Web service by assigning `Nothing` to the property for that Web service.</span></span> <span data-ttu-id="6b40a-125">Metoda ustawiająca właściwości przypisuje `Nothing` przechowywanej wartości.</span><span class="sxs-lookup"><span data-stu-id="6b40a-125">The property setter assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="6b40a-126">Po przypisaniu wartości inne niż `Nothing` do właściwości metody ustawiającej zgłasza <xref:System.ArgumentException> wyjątku.</span><span class="sxs-lookup"><span data-stu-id="6b40a-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="6b40a-127">Można sprawdzić, czy właściwość `My.WebServices` obiekt przechowuje wystąpienie usługi sieci Web przy użyciu `Is` lub `IsNot` operatora.</span><span class="sxs-lookup"><span data-stu-id="6b40a-127">You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="6b40a-128">Te operatory można użyć do sprawdzenia, czy wartość właściwości jest `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6b40a-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b40a-129">Zazwyczaj `Is` lub `IsNot` operator ma odczytać wartości właściwości do porównania.</span><span class="sxs-lookup"><span data-stu-id="6b40a-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="6b40a-130">Jednak jeśli właściwość obecnie przechowuje `Nothing`, właściwość tworzy nowe wystąpienie usługi sieci Web, a następnie zwraca tego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="6b40a-130">However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance.</span></span> <span data-ttu-id="6b40a-131">Jednak kompilator Visual Basic traktuje właściwości `My.WebServices` specjalnie obiektów i umożliwia `Is` lub `IsNot` operatora, aby sprawdzić stan właściwości bez zmiany jego wartość.</span><span class="sxs-lookup"><span data-stu-id="6b40a-131">However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b40a-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="6b40a-132">Example</span></span>  
 <span data-ttu-id="6b40a-133">W tym przykładzie wywołuje `FahrenheitToCelsius` metody `TemperatureConverter` usługi XML sieci Web i zwraca wynik.</span><span class="sxs-lookup"><span data-stu-id="6b40a-133">This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.</span></span>  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 <span data-ttu-id="6b40a-134">Na przykład do pracy projektu musi odwoływać się usługi sieci Web o nazwie `Converter`, i czy usługa sieci Web musi ujawniać `ConvertTemperature` metody.</span><span class="sxs-lookup"><span data-stu-id="6b40a-134">For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method.</span></span> <span data-ttu-id="6b40a-135">Aby uzyskać więcej informacji, zobacz [podczas uzyskiwania dostępu do usługi sieci Web aplikacji](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="6b40a-135">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="6b40a-136">Ten kod nie działa w projekcie aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="6b40a-136">This code does not work in a Web application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b40a-137">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6b40a-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="6b40a-138">Dostępność według typu projektu</span><span class="sxs-lookup"><span data-stu-id="6b40a-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="6b40a-139">Typ projektu</span><span class="sxs-lookup"><span data-stu-id="6b40a-139">Project type</span></span>|<span data-ttu-id="6b40a-140">Dostępne</span><span class="sxs-lookup"><span data-stu-id="6b40a-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="6b40a-141">Aplikacja systemu Windows</span><span class="sxs-lookup"><span data-stu-id="6b40a-141">Windows Application</span></span>|<span data-ttu-id="6b40a-142">**Tak**</span><span class="sxs-lookup"><span data-stu-id="6b40a-142">**Yes**</span></span>|  
|<span data-ttu-id="6b40a-143">Biblioteka klas</span><span class="sxs-lookup"><span data-stu-id="6b40a-143">Class Library</span></span>|<span data-ttu-id="6b40a-144">**Tak**</span><span class="sxs-lookup"><span data-stu-id="6b40a-144">**Yes**</span></span>|  
|<span data-ttu-id="6b40a-145">Aplikacja konsoli</span><span class="sxs-lookup"><span data-stu-id="6b40a-145">Console Application</span></span>|<span data-ttu-id="6b40a-146">**Tak**</span><span class="sxs-lookup"><span data-stu-id="6b40a-146">**Yes**</span></span>|  
|<span data-ttu-id="6b40a-147">Biblioteka formantów systemu Windows</span><span class="sxs-lookup"><span data-stu-id="6b40a-147">Windows Control Library</span></span>|<span data-ttu-id="6b40a-148">**Tak**</span><span class="sxs-lookup"><span data-stu-id="6b40a-148">**Yes**</span></span>|  
|<span data-ttu-id="6b40a-149">Biblioteka formantów sieci Web</span><span class="sxs-lookup"><span data-stu-id="6b40a-149">Web Control Library</span></span>|<span data-ttu-id="6b40a-150">**Tak**</span><span class="sxs-lookup"><span data-stu-id="6b40a-150">**Yes**</span></span>|  
|<span data-ttu-id="6b40a-151">Usługa systemu Windows</span><span class="sxs-lookup"><span data-stu-id="6b40a-151">Windows Service</span></span>|<span data-ttu-id="6b40a-152">**Tak**</span><span class="sxs-lookup"><span data-stu-id="6b40a-152">**Yes**</span></span>|  
|<span data-ttu-id="6b40a-153">Witryna sieci Web</span><span class="sxs-lookup"><span data-stu-id="6b40a-153">Web Site</span></span>|<span data-ttu-id="6b40a-154">Nie</span><span class="sxs-lookup"><span data-stu-id="6b40a-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b40a-155">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b40a-155">See Also</span></span>  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [<span data-ttu-id="6b40a-156">Uzyskiwanie dostępu do usług sieci Web aplikacji</span><span class="sxs-lookup"><span data-stu-id="6b40a-156">Accessing Application Web Services</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)