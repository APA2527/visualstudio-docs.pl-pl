---
title: 'Porady: odblokować program Visual Studio'
ms.date: 07/20/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: ffb580a1-8b5d-48f5-b811-87f8036f50ea
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c3f6bed7cc010f0aeaff22cd46eb7bcaaa4caf6
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44280626"
---
# <a name="how-to-unlock-visual-studio"></a>Porady: odblokować program Visual Studio

Możesz ocenić programu Visual Studio bezpłatnie do 30 dni. Logując się do IDE przedłuża okres próbny 90 dni. Aby nadal korzystać z programu Visual Studio, należy odblokować środowisko IDE przez:

- za pomocą subskrypcją w trybie online

- wprowadzanie klucza produktu

## <a name="to-unlock-visual-studio-using-an-online-subscription"></a>Aby odblokować program Visual Studio przy użyciu subskrypcją w trybie online

Aby odblokować programu Visual Studio przy użyciu subskrypcji programu Visual Studio lub organizacji usługom DevOps platformy Azure skojarzone z kontem Microsoft lub konta służbowego:

1. Kliknij **Zaloguj** przycisk w prawym górnym rogu środowiska IDE (lub przejdź do **pliku** > **ustawienia konta** otworzyć **ustawienia konta**  okno dialogowe i kliknij pozycję **Zaloguj** przycisk).

1. Wprowadź poświadczenia dla konta Microsoft lub konta służbowego lub szkolnego. Program Visual Studio znajdzie subskrypcji programu Visual Studio lub organizację usługom DevOps platformy Azure skojarzony z Twoim kontem.

> [!IMPORTANT]
> Program Visual Studio automatycznie wyszuka skojarzone subskrypcje w trybie online podczas łączenia z organizacji usługom DevOps platformy Azure z **Team Explorer** okna narzędzi. Po nawiązaniu połączenia z organizacją usługi DevOps platformy Azure, możesz zalogować się przy użyciu Microsoft i jej pracy lub kont służbowych. Jeśli istnieje subskrypcją w trybie online dla tego konta użytkownika, Visual Studio automatycznie odblokować środowisko IDE dla Ciebie.

## <a name="to-unlock-visual-studio-with-a-product-key"></a>Aby odblokować program Visual Studio za pomocą klucza produktu

1. Wybierz **pliku** > **ustawienia konta** otworzyć **ustawienia konta** okno dialogowe i kliknij pozycję **licencji za pomocą klucza produktu**łącza.

Wprowadź klucz produktu, w tym miejscu.

> [!TIP]
> Wersje wstępne programu Visual Studio nie ma kluczy produktów. Musisz się zalogować do środowiska IDE programu do użycia wersji wstępnych.

## <a name="address-license-problem-states"></a>Stany problem licencji adresów

### <a name="update-stale-licenses"></a>Aktualizowanie starych licencji

 Można było zaobserwować poniżej komunikat, który licencja jest przestarzałe w programie Visual Studio, który odczytuje, "licencja stała się przestarzała i trzeba ją zaktualizować."

 ![Visual Studio starych licencji wiadomości](../ide/media/vs2017_stale-license.png)

 Ten komunikat oznacza, że gdy Twoja subskrypcja może nadal znajdować się prawidłowy token program Visual Studio używa na bieżąco swoją subskrypcję licencji nie została odświeżona i stała się przestarzała z jednego z następujących powodów:

- Bez użycia programu Visual Studio lub mieli Brak połączenia z Internetem przez dłuższy czas.
- Nastąpiło wylogowanie programu Visual Studio.

Token licencji przejdzie starych, Visual Studio wyświetla najpierw ostrzeżenie komunikat z prośbą o ponowne wprowadzenie poświadczeń.

Jeśli nie ponownie wprowadzić swoje poświadczenia, token rozpoczyna się do starych i **ustawienia konta** okno dialogowe informuje o ile dni pozostało przed pełni wygaśnięcia tokenu. Po wygaśnięciu tokenu programu, należy ponownie wprowadzić swoje poświadczenia dla tego konta lub aktywnej licencji przy użyciu innej metody powyżej, przed kontynuowaniem za pomocą programu Visual Studio.

> [!Important]
> Jeśli używasz programu Visual Studio przez dłuższy czas, w środowiskach o ograniczonym lub Brak dostępu do Internetu, należy użyć klucza produktu odblokować program Visual Studio, aby uniknąć przerw w działaniu.

### <a name="update-expired-licenses"></a>Wygasłe licencji

 Jeśli Twoja subskrypcja wygasła całkowicie i nie jest już prawa dostępu do programu Visual Studio, musisz odnowić subskrypcję lub Dodaj inne konto, które ma subskrypcję. Aby uzyskać więcej informacji o licencji, którego używasz, przejdź do **pliku** > **ustawienia konta** i przyjrzyj się informacje o licencjach po prawej stronie okna dialogowego. Jeśli masz inną subskrypcję skojarzony z innym kontem, należy dodać to konto do **wszystkich kont** liście po lewej stronie okna dialogowego wybierając **Dodaj konto** łącza.

## <a name="see-also"></a>Zobacz także

* [Logowanie do programu Visual Studio](../ide/signing-in-to-visual-studio.md)