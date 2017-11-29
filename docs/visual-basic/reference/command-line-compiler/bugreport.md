---
title: /bugreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7090142f940ae42f554fc0ba16bcc80d8537e38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="bugreport"></a><span data-ttu-id="89421-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="89421-102">/bugreport</span></span>
<span data-ttu-id="89421-103">Tworzy plik, który można używać podczas pliku raport o usterce.</span><span class="sxs-lookup"><span data-stu-id="89421-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89421-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="89421-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="89421-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="89421-105">Arguments</span></span>  
  
|<span data-ttu-id="89421-106">Termin</span><span class="sxs-lookup"><span data-stu-id="89421-106">Term</span></span>|<span data-ttu-id="89421-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="89421-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="89421-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="89421-108">Required.</span></span> <span data-ttu-id="89421-109">Nazwa pliku, który będzie zawierać raport o usterce.</span><span class="sxs-lookup"><span data-stu-id="89421-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="89421-110">Nazwę pliku należy ująć w cudzysłów (""), jeśli nazwa zawiera spację.</span><span class="sxs-lookup"><span data-stu-id="89421-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89421-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="89421-111">Remarks</span></span>  
 <span data-ttu-id="89421-112">Następujące informacje są dodawane do `file`:</span><span class="sxs-lookup"><span data-stu-id="89421-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="89421-113">Kopiowanie wszystkich plików kodu źródłowego w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="89421-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="89421-114">Listy opcji kompilatora używane w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="89421-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="89421-115">Informacje o wersji o kompilatora, środowisko uruchomieniowe języka wspólnego i systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="89421-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="89421-116">Kompilator output, jeśli istnieje.</span><span class="sxs-lookup"><span data-stu-id="89421-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="89421-117">Opis problemu, dla którego zostanie wyświetlony monit.</span><span class="sxs-lookup"><span data-stu-id="89421-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="89421-118">Opis sposobu uważasz, że problem należy ustalić, dla którego zostanie wyświetlony monit.</span><span class="sxs-lookup"><span data-stu-id="89421-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="89421-119">Ponieważ kopię wszystkich plików kodu źródłowego znajduje się w `file`, może zajść potrzeba kodu (podejrzanych) wada najkrótszy program można odtworzyć.</span><span class="sxs-lookup"><span data-stu-id="89421-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="89421-120">`/bugreport` Opcja tworzy plik zawierający potencjalnie wrażliwe informacje.</span><span class="sxs-lookup"><span data-stu-id="89421-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="89421-121">Obejmuje to bieżący czas, wersja kompilatora [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] wersji, wersja systemu operacyjnego, nazwa użytkownika, argumenty wiersza polecenia, z którymi uruchamiania kompilatora, całego kodu źródłowego i forma binarna wszelkie odwołania do zestawu.</span><span class="sxs-lookup"><span data-stu-id="89421-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="89421-122">Ta opcja jest dostępny przez określenie opcji wiersza polecenia w pliku Web.config po stronie serwera zbiór [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89421-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="89421-123">Aby tego uniknąć, należy zmodyfikować plik Machine.config, aby uniemożliwić użytkownikom kompilowanie na serwerze.</span><span class="sxs-lookup"><span data-stu-id="89421-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="89421-124">Jeśli ta opcja jest używana z `/errorreport:prompt`, `/errorreport:queue`, lub `/errorreport:send`, a aplikacja napotka błąd wewnętrzny kompilatora, informacje w `file` są wysyłane do firmy Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="89421-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="89421-125">Informacje te pomogą zidentyfikować przyczynę błędu pracownicy firmy Microsoft i może zwiększyć kolejnej wersji programu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89421-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="89421-126">Domyślnie żadne informacje nie są wysyłane do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89421-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="89421-127">Jednak gdy aplikacja jest skompilować przy użyciu `/errorreport:queue`aplikacji zbiera jego raporty o błędach, które jest domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="89421-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="89421-128">Następnie gdy administrator komputera loguje, system raportowania błędów wyświetla okno podręczne, które umożliwia administratorowi przekazywać do firmy Microsoft raporty wszelkie błędy, że od czasu logowania.</span><span class="sxs-lookup"><span data-stu-id="89421-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89421-129">`/bugreport` Opcja nie jest dostępne w środowisku programowania Visual Studio; będzie dostępna tylko podczas kompilowania z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="89421-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89421-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="89421-130">Example</span></span>  
 <span data-ttu-id="89421-131">Poniższy przykład kompiluje `T2.vb` i umieszcza wszystkie informacje o raportowaniu błędów w pliku `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="89421-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="89421-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="89421-132">See Also</span></span>  
 [<span data-ttu-id="89421-133">Kompilator w wierszu polecenia programu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89421-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="89421-134">/ Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89421-134">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="89421-135">/ errorreport</span><span class="sxs-lookup"><span data-stu-id="89421-135">/errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [<span data-ttu-id="89421-136">Kompilacja przykładów — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="89421-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="89421-137">trustLevel elementu dla securityPolicy (schemat ustawień programu ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="89421-137">trustLevel Element for securityPolicy (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)