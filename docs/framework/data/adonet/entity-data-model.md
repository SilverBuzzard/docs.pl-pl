---
title: Entity Data Model
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69b72a824e6f9468c9b3d86073243d506382e766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model"></a><span data-ttu-id="b1ac7-102">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b1ac7-102">Entity Data Model</span></span>
<span data-ttu-id="b1ac7-103">Modelu danych jednostki (EDM) to zestaw kwestie dotyczące struktury danych, niezależnie od jego przechowywanych formularza.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="b1ac7-104">EDM obiektowy opisanego przez Chen Peterowi w 1976 modelu Relacja jednostki, ale również oparty na modelu Relacja jednostki i zwiększa jego tradycyjnego wykorzystania.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="b1ac7-105">EDM rozwiązuje problemy, które wynikają z danych przechowywanych w wielu formularzach o.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="b1ac7-106">Rozważmy na przykład firma, która przechowuje dane w relacyjnych baz danych, pliki tekstowe, pliki XML, arkusze kalkulacyjne i raporty.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="b1ac7-107">Stawiało to znaczące trudności w modelowania danych, projekt aplikacji i dostępu do danych.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="b1ac7-108">Podczas projektowania aplikacji korzystających z danych, żądania jest napisanie kodu wydajne i łatwy w obsłudze bez ograniczania dostępu do danych wydajne, magazynu i skalowalności.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="b1ac7-109">Jeśli dane relacyjne struktury, są bardzo wydajny dostęp do danych, magazynu i skalowalności, ale pisanie kodu wydajne i łatwy w obsłudze staje się coraz trudniejsze.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="b1ac7-110">Po danych ma strukturę obiektu, są wycofywane kompromisy: pisanie kodu wydajne i łatwy w obsłudze odbywa się kosztem dostępu do danych wydajne, magazynu i skalowalności.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="b1ac7-111">Nawet jeśli znajdują się kompromisu między tymi kompromis, wyzwania wystąpić, gdy dane są przenoszone z jednego formularza do innego.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="b1ac7-112">Modelu danych jednostki uwzględniają te problemy przez opisujące struktury danych pod względem jednostki i relacje, które są niezależne od żadnego schematu magazynu.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="b1ac7-113">Dzięki temu formularzu przechowywanych danych nie ma zastosowania do projektowania aplikacji i opracowywania.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="b1ac7-114">I, ponieważ jednostki i relacje opisano struktury danych, ponieważ jest używany w aplikacji (nie jego przechowywanych formularz), można rozwijać w miarę rozwoju środowisko aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="b1ac7-115">A `conceptual model` jest reprezentację określonej struktury danych jako jednostki i relacje i zazwyczaj jest zdefiniowany w języku specyficznego dla domeny (DSL), który implementuje pojęcia EDM.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="b1ac7-116">[Schematu koncepcyjnego definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) przykładem języka specyficznego dla domeny.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-116">[Conceptual schema definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="b1ac7-117">Jednostki i relacje opisane w modelu koncepcyjnym można traktować jako abstrakcje obiektów i skojarzenia w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="b1ac7-118">Umożliwia deweloperom skoncentrować się na model koncepcyjny bez obawy schemat magazynu i umożliwia im to wydajności i łatwości konserwacji na uwadze do pisania kodu.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="b1ac7-119">W tym samym czasie projektantów schematu magazynu można skoncentrować się na wydajność dostępu do danych, magazynu i skalowalności.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1ac7-120">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="b1ac7-120">In This Section</span></span>  
 <span data-ttu-id="b1ac7-121">Tematy w tej sekcji opisano pojęcia związane z modelu danych jednostki.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="b1ac7-122">Wszelkie DSL, który implementuje EDM powinna zawierać pojęcia opisane w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="b1ac7-123">Należy pamiętać, że [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) używa pliku CSDL, aby zdefiniować modele koncepcyjne.</span><span class="sxs-lookup"><span data-stu-id="b1ac7-123">Note that the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="b1ac7-124">Aby uzyskać więcej informacji, zobacz [specyfikacji pliku CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="b1ac7-124">For more information, see [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="b1ac7-125">Kluczowe założenia modelu danych jednostki</span><span class="sxs-lookup"><span data-stu-id="b1ac7-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="b1ac7-126">Modelu danych jednostki: przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="b1ac7-126">Entity Data Model: Namespaces</span></span>](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="b1ac7-127">Modelu Entity Data Model: Typy danych pierwotnych</span><span class="sxs-lookup"><span data-stu-id="b1ac7-127">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="b1ac7-128">Modelu danych jednostki: dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="b1ac7-128">Entity Data Model: Inheritance</span></span>](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="b1ac7-129">punkt końcowy skojarzenia</span><span class="sxs-lookup"><span data-stu-id="b1ac7-129">association end</span></span>](../../../../docs/framework/data/adonet/association-end.md)  
  
 [<span data-ttu-id="b1ac7-130">skojarzenie liczebność zakończenia</span><span class="sxs-lookup"><span data-stu-id="b1ac7-130">association end multiplicity</span></span>](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [<span data-ttu-id="b1ac7-131">zestawu skojarzeń</span><span class="sxs-lookup"><span data-stu-id="b1ac7-131">association set</span></span>](../../../../docs/framework/data/adonet/association-set.md)  
  
 [<span data-ttu-id="b1ac7-132">Konfigurowanie skojarzenia</span><span class="sxs-lookup"><span data-stu-id="b1ac7-132">association set end</span></span>](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [<span data-ttu-id="b1ac7-133">Typ powiązania</span><span class="sxs-lookup"><span data-stu-id="b1ac7-133">association type</span></span>](../../../../docs/framework/data/adonet/association-type.md)  
  
 [<span data-ttu-id="b1ac7-134">Typ złożony</span><span class="sxs-lookup"><span data-stu-id="b1ac7-134">complex type</span></span>](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [<span data-ttu-id="b1ac7-135">kontenera jednostek</span><span class="sxs-lookup"><span data-stu-id="b1ac7-135">entity container</span></span>](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [<span data-ttu-id="b1ac7-136">klucz jednostki</span><span class="sxs-lookup"><span data-stu-id="b1ac7-136">entity key</span></span>](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [<span data-ttu-id="b1ac7-137">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="b1ac7-137">entity set</span></span>](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [<span data-ttu-id="b1ac7-138">Typ jednostki</span><span class="sxs-lookup"><span data-stu-id="b1ac7-138">entity type</span></span>](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [<span data-ttu-id="b1ac7-139">aspekt</span><span class="sxs-lookup"><span data-stu-id="b1ac7-139">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)  
  
 [<span data-ttu-id="b1ac7-140">Właściwość klucza obcego</span><span class="sxs-lookup"><span data-stu-id="b1ac7-140">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [<span data-ttu-id="b1ac7-141">Funkcja zadeklarowana modelu</span><span class="sxs-lookup"><span data-stu-id="b1ac7-141">model-declared function</span></span>](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [<span data-ttu-id="b1ac7-142">funkcja zdefiniowana przez model</span><span class="sxs-lookup"><span data-stu-id="b1ac7-142">model-defined function</span></span>](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [<span data-ttu-id="b1ac7-143">Właściwość nawigacji</span><span class="sxs-lookup"><span data-stu-id="b1ac7-143">navigation property</span></span>](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [<span data-ttu-id="b1ac7-144">Właściwość</span><span class="sxs-lookup"><span data-stu-id="b1ac7-144">property</span></span>](../../../../docs/framework/data/adonet/property.md)  
  
 [<span data-ttu-id="b1ac7-145">ograniczenie integralności referencyjnej</span><span class="sxs-lookup"><span data-stu-id="b1ac7-145">referential integrity constraint</span></span>](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1ac7-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1ac7-146">See Also</span></span>  
 [<span data-ttu-id="b1ac7-147">ADO.NET Entity Data Model Tools</span><span class="sxs-lookup"><span data-stu-id="b1ac7-147">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="b1ac7-148">Omówienie plików edmx</span><span class="sxs-lookup"><span data-stu-id="b1ac7-148">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="b1ac7-149">Specyfikacja pliku CSDL</span><span class="sxs-lookup"><span data-stu-id="b1ac7-149">CSDL Specification</span></span>](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)