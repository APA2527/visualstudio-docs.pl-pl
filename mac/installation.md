---
title: Install Visual Studio 2019 for Mac
description: Instrukcje dotyczące sposobu instalowania programu Visual Studio 2019 dla systemów Mac i dodatkowe składniki wymagane dla wieloplatformowego opracowywania aplikacji.
author: conceptdev
ms.author: crdun
ms.date: 04/02/2019
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.custom: video
ms.openlocfilehash: 52f9e5f5d21fe69cde613d8e05b365fc8d795dd8
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2019
ms.locfileid: "58857323"
---
# <a name="install-visual-studio-2019-for-mac"></a>Install Visual Studio 2019 for Mac

Aby rozpocząć tworzenie aplikacji programu .NET native, dla wielu platform w systemie macOS, należy zainstalować program Visual Studio 2019 dla komputerów Mac, poniższe kroki.

## <a name="requirements"></a>Wymagania

- Komputer Mac z systemem macOS wysokiej Sierra 10.12 lub nowszej.

Aby kompilować aplikacje Xamarin dla systemu iOS lub macOS, należy także:

- Środowisko Xcode 11.0 lub nowszy. Najnowsza stabilna wersja zazwyczaj jest zalecane.
- Tego identyfikatora firmy Apple. Jeśli nie masz jeszcze identyfikatora Apple ID można utworzyć nowe konto na https://appleid.apple.com. Należy mieć identyfikator Apple ID do instalowania i rejestrowania się w środowisku Xcode.

## <a name="installation-instructions"></a>Instrukcje instalacji

1. Pobierz Instalatora z [program Visual Studio for Mac strony pobierania](https://aka.ms/vsmac).
2. Po ukończeniu pobierania kliknij **VisualStudioforMacInstaller.dmg** Zainstaluj Instalator, następnie uruchom go, klikając dwukrotnie plik logo strzałkę:

    [![CKliknij pozycję dużych strzałkę, aby rozpocząć instalację](media/install-installer-sml.png)](media/install-installer.png#lightbox)

3. Może być przedstawiany z ostrzeżeniem o aplikacji są pobierane z Internetu. Kliknij przycisk **Otwórz**.
4. Zaczekaj, aż Instalator sprawdza, czy system:

    [![THE Instalator sprawdza, czy zainstalowanych składników w systemie](media/install-checking-sml.png)](media/install-checking.png#lightbox)

5. Alert zostanie wyświetlony prośbą o potwierdzenie warunki ochrony prywatności i licencji. Skorzystaj z linków, aby je odczytać, a następnie naciśnij klawisz **Kontynuuj** Jeśli zgadzasz się:

    [![Follow łącza do ochrony prywatności i warunki, następnie kontynuuj, jeśli zgadzasz się](media/install-privacy-sml.png)](media/install-privacy.png#lightbox)

6. Zostanie wyświetlona lista dostępnych obciążeń. Wybierz te, których chcesz użyć:

    [![CWybierz, w której obciążenie opcjonalne funkcje chcesz zainstalować](media/install-selection-sml.png)](media/install-selection.png#lightbox)

7. Po dokonaniu wyborów, naciśnij klawisz **zainstalować** przycisku.
8. Instalator wyświetli postęp pobierania i instalacji programu Visual Studio dla komputerów Mac i wybranego obciążenia. Może zostać wyświetlony o wprowadzenie hasła do przyznawania uprawnień niezbędnych do instalacji.

Jeśli masz problemy z siecią podczas instalowania w środowisku firmowym, zapoznaj się z [instalacji za zaporą lub serwer proxy](https://docs.microsoft.com/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server) instrukcje.

Dowiedz się więcej o zmianach w [informacje o wersji](https://docs.microsoft.com/visualstudio/releasenotes/vs2019-mac-relnotes).

> [!NOTE]
> Wybranego nie zainstalują platformy lub narzędzia podczas oryginalnej instalacji (cofając go w kroku #6), należy uruchomić Instalatora ponownie w razie potrzeby można później dodać składniki.

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Zainstaluj program Visual Studio dla komputerów Mac za serwerem zapory lub serwera proxy

Aby zainstalować program Visual Studio dla komputerów Mac za zaporą, niektóre punkty końcowe muszą być udostępnione w celu pobrania wymagane narzędzia i aktualizacje oprogramowania.

Skonfiguruj sieci, aby zezwolić na dostęp do następujących lokalizacji:

- [Visual Studio punktów końcowych.](/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>Następne kroki

Instalowanie programu Visual Studio dla komputerów Mac pozwala rozpocząć pisanie kodu dla aplikacji. Następujące przewodniki znajdują się przeprowadzenie Cię przez proces w następnych krokach pisania i wdrażania projektów.

### <a name="ios"></a>iOS

1. [Witaj, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [Aprowizowanie urządzenia](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning)(w celu uruchomienia aplikacji na urządzeniu).

### <a name="android"></a>Android

1. [Przy użyciu Menedżera zestawów SDK platformy Xamarin Android](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Emulator zestawu SDK systemu android](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [Konfigurowanie urządzenia na potrzeby programowania](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>Aplikacje platformy .NET core, aplikacje sieci web platformy ASP.NET Core, tworzenia gier Unity

W przypadku innych obciążeń zobacz [obciążeń](/visualstudio/mac/workloads) strony.

## <a name="related-video"></a>Pokrewne wideo

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Acquisition/player]

## <a name="see-also"></a>Zobacz także

- [Zainstaluj program Visual Studio (na Windows)](/visualstudio/install/install-visual-studio)