---
title: Stan pakietu VSPackage | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- state, VSPackages
- VSPackages, managing application state
- state persistence
ms.assetid: 6056a9ea-e7a8-481c-9fc8-340229fa12d9
caps.latest.revision: 25
manager: douge
ms.openlocfilehash: 2891e3f8f9022aad3d16245ae1553a1a9fec3ec7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684195"
---
# <a name="vspackage-state"></a>Stan pakietu VSPackage
Wpływa wiele czynników zbiór wartości trwałe lub stan z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] aplikacji.  
  
-   Projekt ma właściwości projektu i konfiguracji.  
  
-   Rozwiązania mają właściwości.  
  
-   Ustawienia użytkownika określić rozmiar i położenie okna dokumentów, okien narzędzi, stan dokowania i skróty klawiaturowe.  
  
-   Aplikacje mogą mieć opcje, które są ustawiane przez użytkownika.  
  
-   Obiekty utworzone przez aplikację może mieć własne właściwości.  
  
 Oto kilka sposobów, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] stan aplikacji, które mogą być zarządzane:  
  
-   Za pomocą strony właściwości projektu i rozwiązania.  
  
-   Za pomocą **Kreatora importowania i eksportowania ustawień**, który umożliwia użytkownikowi przenoszenie ustawień z jednego komputera na inny.  
  
-   Za pomocą **opcje** okno dialogowe, które zawiera opcje dotyczące aplikacji.  
  
-   Za pomocą **właściwości** okno, które udostępnia właściwości obiektów.  
  
-   Dzięki automatyzacji. Aplikacja ma dostęp do właściwości obiektu i pakietu VSPackage, które została udostępniona z automatyzacją.  
  
 Podstawowy stan aplikacji są różne mechanizmy trwałości, umożliwiające stan aplikacji być zapisywany i przywracany.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Obsługa stanu trwałości](../misc/support-for-state-persistence.md)  
 Zawiera listę typowych strategii zapisywania, przywracania i zresetowanie stanu pakietu VSPackage.  
  
 [Opcje i strony opcji](../extensibility/internals/options-and-options-pages.md)  
 Wprowadza ogólne i niestandardowe strony opcji i objaśnienie sposobu ich wykonania.  
  
 [Tworzenie strony opcji](../extensibility/creating-an-options-page.md)  
 Wyjaśnia, jak utworzyć dwie opcje strony, prostą stronę i niestandardowej strony.  
  
 [Obsługa ustawień kategorii](../misc/support-for-settings-categories.md)  
 W tym artykule omówiono ustawienia użytkownika i jak są tworzone i utrwalone.  
  
 [Tworzenie kategorii ustawień](../extensibility/creating-a-settings-category.md)  
 Wyjaśnia sposób tworzenia [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ustawienia kategorii i użyć go do wartości, aby zapisać i przywrócić wartości z pliku ustawień.  
  
 [Rozszerzanie właściwości i okno właściwości](../extensibility/extending-properties-and-the-property-window.md)  
 Wyjaśnia, jak wyświetlić i zmienić wartość obiektu w **właściwości** okna.  
  
 [Uwidacznianie właściwości w oknie właściwości](../extensibility/exposing-properties-to-the-properties-window.md)  
 Wyjaśnia, jak udostępniać właściwości publiczne obiektu **właściwości** okna.  
  
 [Pomoc techniczna dotycząca właściwości projektu i konfiguracji](../extensibility/internals/support-for-project-and-configuration-properties.md)  
 Wyjaśnia, jak wyświetlić i zmienić właściwości projektu i konfiguracji.  
  
 [Pobieranie właściwości projektu](../extensibility/getting-project-properties.md)  
 Przeprowadzi Cię przez kroki tworzenia zarządzanego pakietu VSPackage, który wyświetla właściwości projektu w oknie narzędzi.  
  
 [Korzystanie z magazynu ustawień](../extensibility/using-the-settings-store.md)  
 Wyjaśnia Store ustawienia mechanizmu stanu trwałego i jak z niej korzystać.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Pakiety VSPackage](../extensibility/internals/vspackages.md)  
 Udostępnia ogólne orientacja do tematów, które opisują sposób tworzenia i używania pakietów VSPackage.