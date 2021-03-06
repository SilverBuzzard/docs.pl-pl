---
title: SqlClient programu Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: 430e0e143519f97802c8cef4eee658b482a81880
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252593"
---
# <a name="sqlclient-for-the-entity-framework"></a>SqlClient programu Entity Framework
W tej sekcji opisano .NET Framework Data Provider for SQL Server (SqlClient), co umożliwia Entity Framework do pracy za pośrednictwem programu Microsoft SQL Server.  
  
## <a name="provider-schema-attribute"></a>Atrybut schematu dostawcy  
 `Provider` jest to atrybut `Schema` element język definicji schematu magazynu (SSDL).  
  
 Użyj SqlClient, należy przypisać do ciągu "System.Data.SqlClient" `Provider` atrybutu `Schema` elementu.  
  
## <a name="providermanifesttoken-schema-attribute"></a>Atrybut schematu ProviderManifestToken  
 `ProviderManifestToken` Wymagany atrybut `Schema` element SSDL. Ten token służy do ładowania manifestu dostawcy dla scenariuszy w trybie offline. Aby uzyskać więcej informacji na temat `ProviderManifestToken` atrybutów, zobacz [elementu schematu (SSDL)](https://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222).  
  
 Klient SQL może służyć jako dostawca danych dla różnych wersji programu SQL Server. Te wersje mają różne możliwości. Na przykład [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] nie obsługuje `varchar(max)` i `nvarchar(max)` typy, które zostały wprowadzone w programie [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].  
  
 Klient SQL tworzy i akceptuje następujące tokeny manifestu dostawcy dla różnych wersji programu SQL Server.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  Począwszy od programu Visual Studio 2010, [narzędzia modelu danych jednostki ADO.NET](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527) nie obsługują programu SQL Server 2000.  
  
## <a name="provider-namespace-name"></a>Nazwa Namespace dostawcy  
 Wszyscy dostawcy należy określić przestrzeni nazw. Ta właściwość zawiera informacje dla programu Entity Framework, który prefiks jest używany przez dostawcę dla określonego konstrukcji, takich jak typy i funkcje. Przestrzeń nazw dla manifestów dostawcy SqlClient jest `SqlServer`. Aby uzyskać więcej informacji na temat przestrzenie nazw, zobacz [przestrzenie nazw](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).  
  
## <a name="types"></a>Types  
 Dostawcy SqlClient programu Entity Framework zawiera informacje dotyczące mapowania między typami modelu koncepcyjnego i typów programu SQL Server. Aby uzyskać więcej informacji, zobacz [SqlClient dla typów programu Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
## <a name="functions"></a>Funkcje  
 Dostawcy SqlClient programu Entity Framework definiuje listę funkcji obsługiwanych przez dostawcę. Aby uzyskać listę obsługiwanych funkcji, zobacz [Klient SQL dla funkcji programu Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Klient SQL dla funkcji programu Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [Klient SQL dla typów programu Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [Znane problemy klienta SQL dla programu Entity Framework](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Jednostki języka SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [Dokumentacja języka](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [Znane problemy w dostawcy SqlClient programu Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
