---
title: 'Porady: Migracja języka specyficznego dla domeny do nowej wersji | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a1ae073-443e-45ca-8bc9-9b944362b449
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: ad5204b4a90018d935028dc517c09ac608043c9a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269428"
---
# <a name="how-to-migrate-a-domain-specific-language-to-a-new-version"></a>Porady: migracja języka specyficznego dla domeny do nowej wersji
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Projekty definiowanie i korzystanie z języka specyficznego dla domeny, które można migrować [!INCLUDE[vs2010](../includes/vs2010-md.md)] z wersji [!INCLUDE[dsl](../includes/dsl-md.md)] który zostało rozpowszechniać za pomocą [!INCLUDE[vs_orcas_long](../includes/vs-orcas-long-md.md)].  
  
 Narzędzie migracji jest dostarczana jako część [!INCLUDE[vssdk_current_long](../includes/vssdk-current-long-md.md)]. Narzędzie konwertuje [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projekty i rozwiązania, które używane lub zdefiniować narzędzia DSL.  
  
 Należy uruchomić narzędzie do migracji jawnie: go nie został uruchomiony automatycznie po otwarciu rozwiązania w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Narzędzia i główny dokument zawierający szczegółowe wskazówki można znaleźć w tej ścieżce:  
  
 **%Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
## <a name="before-you-migrate-your-dsl-projects"></a>Przed przeprowadzeniem migracji projektów języka DSL  
 Narzędzie migracji modyfikuje [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pliki projektu (**.csproj**) i pliki rozwiązania (**.sln**).  
  
#### <a name="to-prepare-projects-for-migration"></a>Aby przygotować projekty do migracji.  
  
-   Upewnij się, że **.csproj** i **.sln** można zapisywać pliki. Jeśli znajdują się pod kontrolą źródła, upewnij się, że ich są wyewidencjonowane.  
  
-   Utwórz kopię foldery, które zamierzasz migrować.  
  
## <a name="migrating-a-collection-of-projects"></a>Migrowanie kolekcji projektów  
  
#### <a name="to-migrate-dsl-projects-and-solutions-to-visual-studio-2010"></a>Aby przeprowadzić migrację DSL projekty i rozwiązania Visual Studio 2010  
  
1.  Uruchom narzędzie do migracji DSL.  
  
    -   Kliknij dwukrotnie narzędzie w Eksploratorze Windows (lub Eksploratora plików) lub uruchomić narzędzie z wiersza polecenia. Narzędzie znajduje się w tej lokalizacji:  
  
         **%ProgramFiles%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
2.  Wybierz folder, który zawiera rozwiązania i projekty, które chcesz przekonwertować.  
  
    -   Wprowadź ścieżkę, w polu u góry strony, narzędzia, lub kliknij przycisk **Przeglądaj**.  
  
     Narzędzie migracji wyświetli drzewa projektów, które zdefiniować lub używać języków DSL. Drzewo obejmuje każdego projektu, który używa **Microsoft.VisualStudio.Modeling.Sdk** lub **texttemplating jest** zestawów.  
  
3.  Przegląd drzewa projektów i usuń zaznaczenie pola wyboru projektów, których nie chcesz konwertować.  
  
    -   Wybierz projekt lub rozwiązanie, aby wyświetlić listę zmian, które spowoduje, że narzędzie.  
  
        > [!NOTE]
        >  Pola wyboru, które pojawiają się obok nazwy folderów nie mają wpływu. Należy rozwinąć foldery, aby sprawdzić, projekty i rozwiązania.  
  
4.  Konwertowanie projektów.  
  
    1.  Kliknij przycisk **przekonwertować**.  
  
         Zanim każdy plik projektu jest konwertowany, kopię _projektu_**.csproj** zostanie zapisany jako _projektu_**. vs2008.csproj**  
  
         Kopia każdego _rozwiązania_**.sln** zostanie zapisany jako _rozwiązania_**. vs2008.sln**  
  
    2.  Badanie zakończone niepowodzeniem konwersje, które są zgłaszane.  
  
         Błędy są zgłaszane w oknie tekstowym. Ponadto widok drzewa pokazuje czerwona flaga w każdym węźle, w której nie można przekonwertować. Możesz kliknąć węzeł, aby uzyskać więcej informacji na temat tego błędu.  
  
5.  **Transformuj wszystkie szablony** rozwiązania zawierającego pomyślnie przekonwertowany projektów.  
  
    1.  Otwórz rozwiązanie.  
  
    2.  Kliknij przycisk **Przekształć wszystkie szablony** przycisku w nagłówku Eksploratora rozwiązań.  
  
        > [!NOTE]
        >  Ten krok można wprowadzić niepotrzebne. Aby uzyskać więcej informacji, zobacz [jak zautomatyzować Przekształć wszystkie szablony](http://msdn.microsoft.com/en-us/b63cfe20-fe5e-47cc-9506-59b29bca768a).  
  
6.  Zaktualizuj niestandardowy kod w projektach przekonwertowana.  
  
    -   Spróbuj kompilować projekty i zbadać wszelkie błędy.  
  
    -   Przetestuj projektanta.  
  
## <a name="see-also"></a>Zobacz też  
 [What's New in Visualisation i Modeling SDK](../misc/what-s-new-in-visualization-and-modeling-sdk.md)



