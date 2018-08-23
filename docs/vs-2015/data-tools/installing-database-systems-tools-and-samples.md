---
title: Instalowanie systemów baz danych, narzędzia i przykłady | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- sample databases
- databases, samples
ms.assetid: 821de34b-eaa9-40af-b9aa-b8305de16899
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1dea5adb6903c7beaf39c65909296224afa2a44c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634273"
---
# <a name="installing-database-systems-tools-and-samples"></a>Instalowanie systemów baz danych, narzędzia i przykłady
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [instalowanie systemów baz danych, narzędzia i przykłady](https://docs.microsoft.com/visualstudio/data-tools/installing-database-systems-tools-and-samples).  
  
  
Visual Studio nie obejmują systemy bazy danych niż te, które są używane wewnętrznie. Do tworzenia aplikacji połączonych danych w programie Visual Studio, zazwyczaj instaluje system bazy danych na lokalnej maszynie do programowania, a następnie wdrażanie aplikacji i baz danych w środowisku produkcyjnym kiedy będą gotowe. System bazy danych, które mają być dostępne z aplikacji platformy .NET i mają być wyświetlane w okna narzędzi danych programu Visual Studio musi on mieć dostawcy danych ADO.NET. Dostawca musi obsługiwać specjalnie Entity Framework, jeśli planowane jest użycie jednostki danych modeli w aplikacji .NET.     Wielu dostawców są oferowane za pośrednictwem Menedżera pakietów NuGet lub za pośrednictwem galerii programu Visual Studio.  
  
 Do tworzenia aplikacji programu SQL upewnij się, że masz zainstalowane w programie Visual Studio program SQL Server Data Tools. Kliknij przycisk **widoku** menu. Jeśli nie widzisz Eksplorator obiektów SQL Server, przejdź do panelu sterowania, a następnie zmienić program Visual Studio. W oknie Instalatora wybierz **programu Microsoft SQL Server Data Tools**.  
  
 Korzystając z interfejsów API usługi Azure Storage, aby uniknąć opłat, dopóki nie będziesz gotowy do wdrożenia w środowisku produkcyjnym należy zainstalować emulatorów usługi Azure storage na komputerze lokalnym podczas programowania. Aby uzyskać więcej informacji, zobacz [korzystanie z emulatora magazynu Azure do tworzenia i testowania](https://azure.microsoft.com/en-us/documentation/articles/storage-use-emulator/).  
  
 Poniższa lista zawiera niektóre z najpopularniejszych systemów bazy danych, które mogą być używane w projektach programu Visual Studio. Lista nie jest wyczerpująca. Aby uzyskać listę dostawców innych firm, które oferują dostawców danych ADO.NET, które umożliwiają ścisłą integrację z narzędzia programu Visual Studio, zobacz [dostawcy danych ADO.NET](https://msdn.microsoft.com/library/dd363565.aspx).  
  
### <a name="microsoft-sql-server"></a>Microsoft SQL Server  
 SQL Server jest baza danych programu Microsoft sztandarowe oferty. SQL Server 2016 zapewnia przełomową wydajność, zabezpieczeniami zaawansowanymi i rozbudowane, zintegrowane raportowania i analizy. Jest on dostarczany w różnych wersjach, które są przeznaczone do różnych celów: z analiz biznesowych o wysokim stopniu skalowalności, wysokiej wydajności, do użycia na jednym komputerze. SQL Server Express jest w pełni funkcjonalna wersja programu SQL Server, które są dopasowane do ponownej dystrybucji i osadzania.  LocalDB to Uproszczona wersja programu SQL Server Express, która nie wymaga konfigurowania i działa w procesie aplikacji. Możesz pobrać jednego lub obu tych produktów z [stronę pobierania programu SQL Server Express](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx).    Wiele przykładów SQL w tej sekcji Użyj programu SQL Server LocalDB. SQL Server Management Studio (SSMS) to aplikacja do zarządzania autonomicznej bazy danych, który ma więcej funkcji niż podana w Eksploratorze obiektów serwera SQL programu Visual Studio. Możesz pobrać program SSMS z poprzedniej konsolidacji.  
  
### <a name="oracle"></a>Oracle  
 Możesz pobrać płatną lub bezpłatnej wersji bazy danych programu Oracle z [sieci technologii Oracle](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index-092322.html) strony. Obsługę projektowania dla programu Entity Framework i TableAdapters, konieczne będzie [Oracle Developer Tools dla programu Visual Studio](http://www.oracle.com/technetwork/developer-tools/visual-studio/overview/index.html). Inne oficjalne produktów Oracle, w tym błyskawiczne wersję klienta Oracle, są dostępne za pośrednictwem Menedżera pakietów NuGet.  Możesz pobrać schematów przykładowej bazy danych Oracle, postępując zgodnie z instrukcjami wyświetlanymi w [dokumentacji Online Oracle](http://docs.oracle.com/cd/E11882_01/server.112/e10831/toc.htm).  
  
### <a name="mysql"></a>MySQL  
 MySQL to system popularnych bazy danych typu open source, który jest powszechnie używana w przedsiębiorstwach i witryn sieci Web. Pliki do pobrania dla MySQL, są MySQL dla programu Visual Studio oraz pokrewne produkty [bazy danych MySQL na Windows](http://www.mysql.com/why-mysql/windows/).  Trzecim oferują różne rozszerzenia programu Visual Studio i zarządzania autonomicznej aplikacji pod kątem MySQL. Możesz przeglądać ofert w Menedżerze pakietów NuGet (**narzędzia** > **Menedżera pakietów NuGet** > **Zarządzaj pakietami NuGet dla rozwiązania**) .  
  
### <a name="postgresql"></a>PostgreSQL  
 PostgreSQL jest systemem relacyjnej bazy danych obiektu bezpłatny, open source. Aby go zainstalować na Windows, możesz ją pobrać z [strony pobierania PostgreSQL](http://www.postgresql.org/download/windows/).  Można także utworzyć PostgreSQL z kodu źródłowego.  PostgreSQL podstawowego systemu obejmuje interfejs języka C. Wiele firm Obejmij pakietów NuGet za pomocą PostgreSQL z poziomu aplikacji .NET.  Możesz przeglądać ofert w Menedżerze pakietów NuGet (**narzędzia** > **Menedżera pakietów NuGet** > **Zarządzaj pakietami NuGet dla rozwiązania**) . Prawdopodobnie najpopularniejsze pakietu są dostarczane przez [npgsql.org](http://www.npgsql.org).  
  
### <a name="sqlite"></a>Bazy danych SQLite  
 Bazy danych SQLite jest osadzony aparat bazy danych SQL działa w procesie własnych aplikacji. Możesz ją pobrać z [strony pobierania oprogramowania SQLite](http://www.sqlite.org/download.html). Dostępne są także wiele innych pakietów NuGet dla bazy danych SQLite. Możesz przeglądać ofert w Menedżerze pakietów NuGet (**narzędzia** > **Menedżera pakietów NuGet** > **Zarządzaj pakietami NuGet dla rozwiązania**) .  
  
### <a name="firebird"></a>Firebird  
 Firebird to system bazy danych SQL typu open source. Możesz ją pobrać z [strony pobierania Firebird](http://firebirdsql.org/en/downloads/). Dostawca danych programu ADO.NET jest dostępna za pośrednictwem Menedżera pakietów NuGet.  
  
## <a name="see-also"></a>Zobacz też  
 [Jak określić wersję i wydanie programu SQL Server i jego składników](http://support.microsoft.com/kb/321185)

