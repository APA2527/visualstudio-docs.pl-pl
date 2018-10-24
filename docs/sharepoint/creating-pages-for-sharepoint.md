---
title: Tworzenie stron dla SharePoint | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, master pages
- SharePoint development in Visual Studio, page layouts
- SharePoint development in Visual Studio, content pages
- master pages[SharePoint development in Visual Studio], designing
- content pages[SharePoint development in Visual Studio], designing
- page layouts[SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ecdbde69735f548b7ab70da132e9e2cc2080bbcb
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326053"
---
# <a name="create-pages-for-sharepoint"></a>Tworzenie stron dla SharePoint
W programie SharePointmMożna utworzyć strony aplikacji, strony w witrynie, strony wzorcowe i układy stron witryny programu SharePoint.  
  
Strony aplikacji można tworzyć za pomocą szablonu w programie Visual Studio. Tworzenie stron w witrynie, stron wzorcowych i układów stron jest możliwe za pomocą programu SharePoint Designer. Następnie można zaimportować te strony do programu Visual Studio, aby korzystać z nich w projekcie programu SharePoint.  
  
Można również zmodyfikować wygląd i działanie stron przy użyciu kaskadowych arkuszy stylów, ECMAScript i motywów. 
  
## <a name="types-of-sharepoint-pages"></a>Typy strony programu SharePoint
 W poniższej tabeli opisano cztery typy stron, które zawiera witryny programu SharePoint. 
  
|Typ strony|Opis|  
|---------------|-----------------|  
|Strony aplikacji|Utwórz stronę aplikacji, jeśli strona ma zawierać kod niestandardowy lub ma być udostępniana w wielu lokacjach. W przeciwnym razie strona witryny może być najlepszym rozwiązaniem.| 
|Strony witryny|Utwórz stronę witryny, jeśli chcesz wykonać jedno z następujących zadań:<br /><br />— Dodanie strony do biblioteki programu SharePoint.<br />— Umożliwienie stronie hostowania funkcji, takich jak dynamiczne składniki Web Part i strefy składników Web Part.<br />— Umożliwienie użytkownikom dostosowywania strony przy użyciu programu SharePoint Designer.<br /><br /> Nie należy tworzyć strony witryny, jeśli strona ma zawierać kod niestandardowy. Mimo że można dodać kod niestandardowy do strony witryny, kod przestanie działać, kiedy użytkownik dostosuje stronę za pomocą programu SharePoint Designer.| 
|Strony główne|Tworzenie strony głównej, jeśli chcesz zdefiniować wspólnej struktury strony witryny i stron aplikacji.|  
|Układy stron|Układy stron są specyficzne dla [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] i umożliwiają uściślić wspólnej struktury witryny i stron aplikacji.|  
  
 Omówienie każdego typu strony, zobacz [bloków konstrukcyjnych: stron i interfejs użytkownika](http://go.microsoft.com/fwlink/?LinkID=182095), i [układy stron i stron wzorcowych](http://go.microsoft.com/fwlink/?LinkID=182096).  
  
## <a name="create-application-pages"></a>Tworzenie stron aplikacji
 Można utworzyć strony aplikacji w programie Visual Studio, dodając **strony aplikacji** elementu do projektu programu SharePoint. Na stronie Dodaj formanty i następnie obsługę zdarzeń formantu przez dodanie kodu.  
  
 Można ustawić punkty przerwania w pliku kodu strony, uruchomienia debugera i przetestować w lokalnej witrynie programu SharePoint bez żadnych dodatkowych czynności konfiguracyjnych. Aby uzyskać więcej informacji, zobacz [tworzenie stron aplikacji dla programu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
## <a name="create-site-pages-master-pages-and-page-layouts"></a>Tworzenie stron w witrynie, stron wzorcowych i układy stron
 Można utworzyć strony witryny, stron wzorcowych i układy stron za pomocą programu SharePoint Designer. Następnie można zaimportować te strony do programu Visual Studio. Jeśli chcesz skorzystać z wdrożenia lub funkcje kontroli źródła, które są dostępne w programie Visual Studio, należy zaimportować strony. Aby uzyskać więcej informacji, zobacz [Importowanie elementów z istniejącej witryny SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).  
  
 Ponieważ trudno jest modyfikować te strony po zaimportowaniu, należy je projektować przed zaimportowaniem.
  
## <a name="create-cascading-style-sheets-ecmascript-and-themes"></a>Tworzenie kaskadowych arkuszy stylów, ECMAScript i motywów
 Visual Studio nie ma szablonów do tworzenia kaskadowych arkuszy stylów (CSS), skryptów ECMAScript (JavaScript, JScript) lub plików motywu witryny programu SharePoint. Pliki te można utworzyć za pomocą wskazówek, które są dostępne w zestawie SDK programu SharePoint. lub za pomocą narzędzi, takich jak SharePoint Designer. 
  
 Te pliki można dodać bezpośrednio do rozwiązania lub można je zaimportować. W obu przypadkach należy utworzyć odpowiednie foldery zamapowanego dla każdego elementu, który zostanie dodany. Aby uzyskać więcej informacji na temat tworzenia zamapowany folder, zobacz [porady: Dodawanie i usuwanie folderów mapowanych](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
 Aby uzyskać więcej informacji o tworzeniu kaskadowych arkuszy stylów, zobacz [kaskadowych styl arkusze klasy użycia w programie SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkID=182098). Aby uzyskać więcej informacji o tworzeniu plików JavaScript i JScript dla rozwiązania programu SharePoint, zobacz [ustawienia zapasowej ASPX strony podstawowej dla języka ECMAScript](http://go.microsoft.com/fwlink/?LinkID=182099). Aby uzyskać więcej informacji na temat tematów, zobacz [bloków konstrukcyjnych: stron i interfejs użytkownika](http://go.microsoft.com/fwlink/?LinkID=182095).  
  
## <a name="related-topics"></a>Tematy pokrewne
  
|Tytuł|Opis|  
|-----------|-----------------|  
|[Tworzenie stron aplikacji dla programu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)|Opisuje sposób dodawania strony aplikacji: *.aspx* zawartość, która jest scalany z strony wzorcowej programu SharePoint.|  
|[Porady: Tworzenie strony aplikacji](../sharepoint/how-to-create-an-application-page.md)|Pokazuje, jak utworzyć stron ASP.NET, które są uruchamiane w witrynie programu SharePoint.|  
|[Wskazówki: Tworzenie strony aplikacji SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)|Pokazuje, jak projektować i debugowania na stronie sieci Web platformy ASP.NET dla witryny programu SharePoint.|  
  
