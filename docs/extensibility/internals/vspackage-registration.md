---
title: Rejestracja pakietu VSPackage | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: ecd20da8-b04b-4141-a8f4-a2ef91dd597a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 29592f7956177a4894967d7f393605a54f7ec07b
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39513164"
---
# <a name="vspackage-registration"></a>Rejestracja pakietu VSPackage
Poinformowanie pakietów VSPackage [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] są zainstalowane i powinny zostać załadowany. Ten proces odbywa się przez zapisywania informacji w rejestrze. To typowe zadanie Instalatora.  
  
> [!NOTE]
>  Jest akceptowana praktyka podczas programowania pakietu VSPackage, aby użyć rejestracji automatycznej. Jednak [!INCLUDE[vsipprvsip](../../extensibility/includes/vsipprvsip_md.md)] partnerów nie można wysłać ich produktów w ramach instalacji za pomocą rejestracji automatycznej.  
  
 Rejestr w pakiet Instalatora Windows jest ogólnie wpisów w tabeli w rejestrze. Można również zarejestrować rozszerzeń plików, w tabeli w rejestrze. Jednak Instalator Windows udostępnia wbudowaną obsługę identyfikator programowy (ProgId), klasy, rozszerzenia i tabele zlecenie. Aby uzyskać więcej informacji, zobacz [tabel bazy danych](/windows/desktop/Msi/database-tables).  
  
 Pamiętaj, że wpisy rejestru są skojarzone ze składnikiem, który jest odpowiedni dla wybranej strategii side-by-side. Na przykład wpisy rejestru dla pliku udostępnionego, powinna być skojarzona z tego pliku Instalatora Windows składnika. Podobnie wpisy rejestru dla określonej wersji pliku powinna być skojarzona z tego pliku składnika. W przeciwnym razie Instalowanie lub odinstalowywanie Twojego pakietu VSPackage dla jednej wersji [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] może spowodować przerwanie usługi pakietu VSPackage w innych wersjach. Aby uzyskać więcej informacji, zobacz [obsługi wielu wersji programu Visual Studio](../../extensibility/supporting-multiple-versions-of-visual-studio.md)  
  
> [!NOTE]
>  Najprostszym sposobem na Zarządzanie rejestracją jest używać tych samych danych w tych samych plików zarówno dla rejestracji dla deweloperów i rejestracji czas instalacji. Na przykład niektóre narzędzia do programowania Instalator może zużywać plik w formacie reg w czasie kompilacji. Jeśli deweloperzy przechowują pliki reg własne codziennych opracowywania i debugowania, tych samych plików mogą być zawarte w Instalatorze automatycznie. Jeśli nie można automatycznie udostępnić dane rejestracyjne, upewnij się, że Instalatora kopię danych rejestracji jest aktualna.  
  
## <a name="registering-unmanaged-vspackages"></a>Rejestrowanie pakietów VSPackage niezarządzanych  
 Niezarządzane pakietów VSPackage (włącznie z wygenerowanymi przez szablon pakietu Visual Studio) umożliwia przechowywanie informacji o rejestracji plików .rgs ATL-style. Format pliku .rgs jest przeznaczony dla biblioteki ATL i zazwyczaj nie mogą być używane jako-polega na instalacji narzędzia do tworzenia treści. Informacje o rejestracji dla Instalatora pakietu VSPackage musi być obsługiwany osobno. Na przykład deweloperzy mogą synchronizowania plików w formacie reg za pomocą .rgs zmian w plikach. Plików reg można scalić z RegEdit prace deweloperskie lub używane przez Instalatora.  
  
## <a name="registering-managed-vspackages"></a>Rejestrowanie pakietów VSPackage zarządzanych  
 Narzędzie RegPkg odczytuje atrybuty rejestracji z zarządzanego pakietu VSPackage i albo zapisywać informacje bezpośrednio do rejestru lub zapisu reg formatu plików, które mogą być używane przez Instalatora.  
  
> [!NOTE]
>  Narzędzie RegPkg nie jest do dystrybucji i nie można zarejestrować pakietu VSPackage w systemie użytkownika.  
  
## <a name="why-vspackages-should-not-self-register-at-install-time"></a>Dlaczego pakietów VSPackage nie powinno rejestrować samodzielnie w czasie instalacji  
 Twoje pliki instalacyjne pakietu VSPackage nie należy polegać na rejestracji automatycznej. Na pierwszy rzut oka pamiętając wartości rejestru pakietu VSPackage tylko pakietu VSPackage, sama prawdopodobnie dobrym pomysłem. Biorąc pod uwagę, że deweloperzy muszą dostępne wartości rejestru do wykonywania rutynowych pracy i testowania, dobrym pomysłem będzie uniknąć utrzymywanie oddzielną kopię danych rejestru w Instalatorze. Instalator może polegać na VSPackage można zapisać wartości rejestru.  
  
 Podczas dobre teorii Autorejestracja ma kilka wad, które nie nadaje się do instalacji pakietu VSPackage:  
  
-   Poprawnie obsługi instalacji, odinstalowywania, wycofywanie instalacji i dezinstalacji wycofywania wymaga utworzenia cztery akcje niestandardowe dla każdego zarządzanego pakietu VSPackage samodzielnie rejestruje przez wywołanie metody RegPkg.  
  
-   Swoje podejście do działu pomocy technicznej side-by-side mogą wymagać zredagujesz cztery akcje niestandardowe, które wywołują RegSvr32 lub RegPkg dla każdej obsługiwanej wersji programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   Instalacja z własnym zarejestrowany moduł nie może bezpiecznie wycofana, ponieważ nie istnieje sposób z informacją, jeśli zarejestrują klucze są używane przez inną funkcję lub aplikację.  
  
-   Biblioteki DLL zarejestrują połączyć czasami pomocnicze w ramach biblioteki dll, które nie są obecne lub niewłaściwej wersji. Z kolei Instalator Windows można zarejestrować biblioteki DLL przy użyciu tabel rejestru za pomocą niezależne od bieżącego stanu systemu.  
  
-   Można odmówić dostępu do zasobów sieciowych, takich jak biblioteki typów, jeśli składnik jest określony jako przebieg ze źródła i znajduje się w tabeli SelfReg kodu rejestracji automatycznej. Może to spowodować, że instalacja składnika się kończyć niepowodzeniem podczas instalacji administracyjnej.  
  
## <a name="see-also"></a>Zobacz też  
 [Instalator Windows](/windows/desktop/Msi/windows-installer-portal)   
 [Rejestracja pakietu zarządzanego](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)