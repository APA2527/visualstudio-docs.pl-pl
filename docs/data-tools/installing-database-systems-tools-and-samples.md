---
title: Zgodność bazy danych
description: Przejrzyj zgodne systemy baz danych dla programu Visual Studio, takie jak Microsoft SQL Server, Oracle, MySQL, PostgreSQL, SQLite i Firebird.
ms.custom: SEO-VS-2020
ms.date: 09/06/2017
ms.topic: conceptual
helpviewer_keywords:
- database systems
- database compatibility
- databases for Visual Studio
ms.assetid: 821de34b-eaa9-40af-b9aa-b8305de16899
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- data-storage
ms.openlocfilehash: 41cf31c6cae310eb151969df0776788d6ea5b1e1
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99866700"
---
# <a name="compatible-database-systems-for-visual-studio"></a>Zgodne systemy baz danych dla programu Visual Studio

Aby opracować aplikację podłączoną do danych w programie Visual Studio, zazwyczaj należy zainstalować system bazy danych na lokalnym komputerze deweloperskim, a następnie wdrożyć aplikację i bazę danych w środowisku produkcyjnym, gdy będą gotowe. Program Visual Studio instaluje SQL Server Express LocalDB na komputerze jako część obciążenia **magazynu i przetwarzania danych** . To wystąpienie LocalDB jest przydatne do szybkiego i łatwego opracowywania aplikacji połączonych z danymi.

Aby można było uzyskać dostęp do systemu bazy danych z aplikacji .NET i były one widoczne w oknach narzędzi danych programu Visual Studio, musi on mieć dostawcę danych ADO.NET. Dostawca musi w specjalny sposób obsługiwać Entity Framework, jeśli planujesz używać modeli danych Entity w aplikacji .NET. Wielu dostawców jest oferowany za pomocą Menedżera pakietów NuGet lub Visual Studio Marketplace.

Jeśli używasz interfejsów API usługi Azure Storage, zainstaluj emulatory usługi Azure Storage na maszynie lokalnej podczas opracowywania, aby uniknąć naliczania opłat do momentu, aż wszystko będzie gotowe do wdrożenia w środowisku produkcyjnym. Aby uzyskać więcej informacji, zobacz [Używanie emulatora usługi Azure Storage do programowania i testowania](/azure/storage/common/storage-use-emulator).

Poniższa lista zawiera niektóre z bardziej popularnych systemów baz danych, które mogą być używane w projektach programu Visual Studio. Lista nie jest wyczerpująca. Aby zapoznać się z listą innych dostawców, którzy oferują ADO.NET dostawcy danych, którzy umożliwiają ścisłą integrację z narzędziami programu Visual Studio, zobacz [ADO.NET dostawcy danych](/dotnet/framework/data/adonet/data-providers).

## <a name="microsoft-sql-server"></a>Microsoft SQL Server

SQL Server to oferta bazy danych Microsoft sztandarowe. SQL Server 2016 zapewnia przełomową wydajność, zaawansowane zabezpieczenia i rozbudowane, zintegrowane raportowanie i analizę. Jest ona dostarczana w różnych wersjach, które są przeznaczone do różnych celów: od wysoce skalowalnej i wysokiej wydajności analizy biznesowej do użycia na pojedynczym komputerze. SQL Server Express to w pełni funkcjonalna wersja SQL Server, która jest dostosowana do redystrybucji i osadzania.  LocalDB to uproszczona wersja SQL Server Express, która nie wymaga konfiguracji i jest uruchamiana w procesie aplikacji. Możesz pobrać albo oba produkty ze [strony pobierania SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express). Wiele przykładów SQL w tej sekcji używa SQL Server LocalDB. SQL Server Management Studio (SSMS) to autonomiczna aplikacja do zarządzania bazami danych, która ma więcej funkcji niż podano w programie Visual Studio Eksplorator obiektów SQL Server. Możesz pobrać narzędzie SSMS z poprzedniego linku.

## <a name="oracle"></a>Oracle

Na stronie [sieci technologii Oracle](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html) można pobrać płatną lub bezpłatną wersję bazy danych Oracle. Aby zapewnić obsługę Entity Framework i TableAdapters, potrzebne są [Narzędzia programistyczne Oracle dla programu Visual Studio](https://www.oracle.com/database/technologies/developer-tools/visual-studio/). Inne oficjalne produkty firmy Oracle, w tym klient wiadomości błyskawicznych Oracle, są dostępne za pomocą Menedżera pakietów NuGet. Przykładowe schematy programu Oracle można pobrać, postępując zgodnie z instrukcjami w [dokumentacji usługi Oracle online](https://docs.oracle.com/cd/E11882_01/server.112/e10831/toc.htm).

## <a name="mysql"></a>MySQL

MySQL to popularny system baz danych typu "open source", który jest powszechnie używany w przedsiębiorstwach i witrynach sieci Web. Pliki do pobrania dla programu MySQL, MySQL dla programu Visual Studio i powiązane produkty są dostępne w witrynie [MySQL w systemie Windows](https://www.mysql.com/why-mysql/windows/). Osoby trzecie oferują różne rozszerzenia programu Visual Studio i autonomiczne aplikacje zarządzania dla programu MySQL. Oferty można przeglądać w Menedżerze pakietów NuGet (**Narzędzia**  >  **Menedżera pakietów** NuGet  >  **Zarządzanie pakietami NuGet dla rozwiązania**).

## <a name="postgresql"></a>PostgreSQL

PostgreSQL to bezpłatny system relacyjnej bazy danych typu "open source". Aby zainstalować ją w systemie Windows, można pobrać ją ze [strony pobierania PostgreSQL](https://www.postgresql.org/download/windows/). Możesz również kompilować PostgreSQL z kodu źródłowego. System PostgreSQL Core zawiera interfejs języka C. Wiele stron trzecich udostępnia pakiety NuGet do używania PostgreSQL z aplikacji .NET. Oferty można przeglądać w Menedżerze pakietów NuGet (**Narzędzia**  >  **Menedżera pakietów** NuGet  >  **Zarządzanie pakietami NuGet dla rozwiązania**). Prawdopodobnie najpopularniejszy pakiet jest dostarczany przez [npgsql.org](http://www.npgsql.org).

## <a name="sqlite"></a>SQLite

SQLite to osadzony aparat bazy danych SQL, który działa w procesie aplikacji. Można go pobrać ze [strony pobierania oprogramowania SQLite](https://www.sqlite.org/download.html). Dostępne są również wiele pakietów NuGet innych firm dla oprogramowania SQLite. Oferty można przeglądać w Menedżerze pakietów NuGet (**Narzędzia**  >  **Menedżera pakietów** NuGet  >  **Zarządzanie pakietami NuGet dla rozwiązania**).

## <a name="firebird"></a>Firebird

Firebird to system bazy danych SQL Open Source. Można go pobrać ze [strony pobierania Firebird](http://firebirdsql.org/en/downloads/). Dostawca danych ADO.NET jest dostępny za pomocą Menedżera pakietów NuGet.

## <a name="see-also"></a>Zobacz też

- [Uzyskiwanie dostępu do danych w programie Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
- [Jak określić wersję i wydanie SQL Server i jej składników](https://support.microsoft.com/help/321185/how-to-determine-the-version-edition-and-update-level-of-sql-server-an)
