---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 403c7a50bcb802140bb008bd18db0a6f16663942
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504733"
---
# <a name="dbproviderfactories"></a>DbProviderFactories
<xref:System.Data.Common> Nazw zawiera klasy do tworzenia <xref:System.Data.Common.DbProviderFactory> wystąpień do pracy z konkretnych źródeł danych. Po utworzeniu <xref:System.Data.Common.DbProviderFactory> wystąpienia i przekazać go informacje o dostawcy danych `DbProviderFactory` można określić obiekt połączenia poprawny, silnie typizowaną do zwrócenia na podstawie informacji został dostarczony.  
  
 Począwszy od programu .NET Framework w wersji 4, dostawców danych takich jak <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, i <xref:System.Data.OracleClient> już nie są wymienione w pliku machine.config, ale niestandardowego dostawcy będą nadal będą wyświetlane istnieje.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Omówienie modelu fabryki](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 Zawiera omówienie wzorca projektowego fabryki i interfejs programowania.  
  
 [Uzyskiwanie DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 Pokazuje, jak listy dostawcy danych zainstalowanego i tworzenia <xref:System.Data.Common.DbConnection> z `DbProviderFactory`.  
  
 [DbConnection, DbCommand i DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 Przedstawia sposób tworzenia <xref:System.Data.Common.DbCommand> i <xref:System.Data.Common.DbDataReader>i sposób obsługi błędów danych przy użyciu <xref:System.Data.Common.DbException>.  
  
 [Modyfikowanie danych za pomocą obiektu DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 Pokazuje sposób użycia <xref:System.Data.Common.DbCommandBuilder> z <xref:System.Data.Common.DbDataAdapter> do pobrania i modyfikowania danych.  
  
## <a name="see-also"></a>Zobacz też  
 [Pobieranie i modyfikowanie danych ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET zarządzanego dostawcy i Centrum deweloperów zestawu danych](https://go.microsoft.com/fwlink/?LinkId=217917)
