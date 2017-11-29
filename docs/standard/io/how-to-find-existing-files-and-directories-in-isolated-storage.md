---
title: "Porady: wyszukiwanie istniejących plików i katalogów w izolowanym magazynie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a><span data-ttu-id="15f72-102">Porady: wyszukiwanie istniejących plików i katalogów w izolowanym magazynie</span><span class="sxs-lookup"><span data-stu-id="15f72-102">How to: Find Existing Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="15f72-103">Aby wyszukać katalog w magazynie izolowanym, użyj <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="15f72-103">To search for a directory in isolated storage, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="15f72-104">Ta metoda przyjmuje ciąg, który reprezentuje wzorzec wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="15f72-104">This method takes a string that represents a search pattern.</span></span> <span data-ttu-id="15f72-105">Można użyć zarówno jednoznakowym (?) i wielu znaków (*) znaki symboli wieloznacznych we wzorcu wyszukiwania, ale symboli wieloznacznych musi występować w końcowa część nazwy.</span><span class="sxs-lookup"><span data-stu-id="15f72-105">You can use both single-character (?) and multi-character (*) wildcard characters in the search pattern, but the wildcard characters must appear in the final portion of the name.</span></span> <span data-ttu-id="15f72-106">Na przykład `directory1/*ect*` jest prawidłowy ciąg wyszukiwania, ale `*ect*/directory2` nie jest.</span><span class="sxs-lookup"><span data-stu-id="15f72-106">For example, `directory1/*ect*` is a valid search string, but `*ect*/directory2` is not.</span></span>  
  
 <span data-ttu-id="15f72-107">Aby wyszukać plik, użyj <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="15f72-107">To search for a file, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="15f72-108">Ograniczenie dla symbole wieloznaczne w ciągach wyszukiwania, których dotyczy <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> dotyczą również <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span><span class="sxs-lookup"><span data-stu-id="15f72-108">The restriction for wildcard characters in search strings that applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> also applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span></span>  
  
 <span data-ttu-id="15f72-109">Żadna z tych metod jest rekursywny; <xref:System.IO.IsolatedStorage.IsolatedStorageFile> klasa nie dostarcza żadnych metod do wyświetlania listy wszystkich katalogów lub plików w magazynie.</span><span class="sxs-lookup"><span data-stu-id="15f72-109">Neither of these methods is recursive; the <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class does not supply any methods for listing all directories or files in your store.</span></span> <span data-ttu-id="15f72-110">Jednak rekursywny metod przedstawiono w poniższym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="15f72-110">However, recursive methods are shown in the following code example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15f72-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="15f72-111">Example</span></span>  
 <span data-ttu-id="15f72-112">Poniższy przykładowy kod ilustruje sposób tworzenia plików i katalogów w izolowanym magazynie.</span><span class="sxs-lookup"><span data-stu-id="15f72-112">The following code example illustrates how to create files and directories in an isolated store.</span></span> <span data-ttu-id="15f72-113">Najpierw należy pobrać i umieszczane w sklepu, która jest odizolowana dla użytkownika, domena i zestawu `isoStore` zmiennej.</span><span class="sxs-lookup"><span data-stu-id="15f72-113">First, a store that is isolated for user, domain, and assembly is retrieved and placed in the `isoStore` variable.</span></span> <span data-ttu-id="15f72-114"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> Metoda jest używana do konfigurowania kilku różnych katalogach i <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> Konstruktor tworzy niektóre pliki w tych katalogach.</span><span class="sxs-lookup"><span data-stu-id="15f72-114">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> method is used to set up a few different directories, and the <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> constructor creates some files in these directories.</span></span> <span data-ttu-id="15f72-115">Kod następnie pętli wyniki `GetAllDirectories` metody.</span><span class="sxs-lookup"><span data-stu-id="15f72-115">The code then loops through the results of the `GetAllDirectories` method.</span></span> <span data-ttu-id="15f72-116">Ta metoda używa <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> można znaleźć nazwy katalogów w bieżącym katalogu.</span><span class="sxs-lookup"><span data-stu-id="15f72-116">This method uses <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> to find all the directory names in the current directory.</span></span> <span data-ttu-id="15f72-117">Te nazwy są przechowywane w tablicy, a następnie `GetAllDirectories` wywołuje, przekazując każdego katalogu znaleziono.</span><span class="sxs-lookup"><span data-stu-id="15f72-117">These names are stored in an array, and then `GetAllDirectories` calls itself, passing in each directory it has found.</span></span> <span data-ttu-id="15f72-118">W związku z tym zwracane są wszystkie nazwy katalogów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="15f72-118">As a result, all the directory names are returned in an array.</span></span> <span data-ttu-id="15f72-119">Następnie kod wywołuje `GetAllFiles` metody.</span><span class="sxs-lookup"><span data-stu-id="15f72-119">Next, the code calls the `GetAllFiles` method.</span></span> <span data-ttu-id="15f72-120">Ta metoda wywołuje `GetAllDirectories` Aby dowiedzieć się, nazwy wszystkich katalogów, a następnie sprawdza każdy katalog dla plików przy użyciu <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="15f72-120">This method calls `GetAllDirectories` to find out the names of all the directories, and then it checks each directory for files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> method.</span></span> <span data-ttu-id="15f72-121">Wynik jest zwracany w tablicy do wyświetlenia.</span><span class="sxs-lookup"><span data-stu-id="15f72-121">The result is returned in an array for display.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="15f72-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="15f72-122">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="15f72-123">Izolowany Magazyn</span><span class="sxs-lookup"><span data-stu-id="15f72-123">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)