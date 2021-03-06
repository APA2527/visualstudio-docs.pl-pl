---
title: Menedżer pakietów dla języka R
description: Jak używać Menedżera pakietów języka R w programie Visual Studio do instalowania i zarządzania pakietami języka R.
ms.date: 01/24/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: d35bfd45e862912ff78ae600eed01ce8dc002493
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "62998859"
---
# <a name="package-manager"></a>Menedżer pakietów

Menedżer pakietów R Tools for Visual Studio (RTVS) jest interfejsem użytkownika do zarządzania pakietami języka R. Aby go otworzyć, wybierz pozycję **R Tools**  >  pakiety**systemu Windows**  >  **Packages** lub naciśnij klawisz **Ctrl** + **7**.

Menedżer pakietów ma trzy karty. Każda karta wyświetla listę odpowiednich pakietów po lewej stronie i szczegółowe informacje dotyczące wybranego pakietu po prawej stronie, w tym wersję pakietu, opis, licencję, lokalizację instalacji i linki do innych istotnych informacji. Pole wyszukiwania w prawym górnym rogu umożliwia filtrowanie listy.

> [!Tip]
> Termin w polu wyszukiwania będzie obowiązywać podczas przełączania między kartami.

- Opcja **dostępne** umożliwia przeglądanie pakietów do zainstalowania. Jeśli pakiet jest już zainstalowany, przycisk **Instaluj** po prawej stronie zmienia się na **Odinstaluj**.

    ![Karta dostępne pakiety w Menedżerze pakietów R Tools for Visual Studio](media/package-manager-available.png)

- **Zainstalowane** programy pokazują wszystkie zainstalowane i załadowane pakiety. Zielona kropka obok pakietu wskazuje, że jest załadowana do sesji języka R. Ikona Red X na liście po lewej stronie lub przycisk **Odinstaluj** po prawej stronie może służyć do odinstalowania pakietu. Jeśli dostępna jest nowsza wersja zainstalowanego pakietu, zostanie wyświetlona niebieska strzałka w górę z prawej strony pakietu.

    ![Karta zainstalowane pakiety w Menedżerze pakietów R Tools for Visual Studio](media/package-manager-installed.png)

- **Załadowano** są wyświetlane tylko te pakiety, które są ładowane do sesji języka R, z których wszystkie są wyświetlane z zieloną kropką. W tym miejscu można również odinstalować i zaktualizować pakiety.

    ![Karta załadowane pakiety w Menedżerze pakietów R Tools for Visual Studio](media/package-manager-loaded.png)

## <a name="package-locations"></a>Lokalizacje pakietów

Pakiety są instalowane w następujących lokalizacjach:

- Pakiety podstawowe dołączone do RTVS są instalowane w *katalogu C:\Program Files\Microsoft\R Client \ R_SERVER \library*
- Dodatkowe pakiety są instalowane w *%USERPROFILE%\Documents\R\win-library\3.3*
