---
title: Projektowanie tabeli poleceń XML (. Pliki Vsct) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, designing
ms.assetid: bb87a322-bac4-4258-92bc-9a876f05d653
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b7a28e8ea14d27eb96100a4f1f67a875746dc5f6
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39499266"
---
# <a name="design-xml-command-table-vsct-files"></a>Projektowanie plików (vsct) tabeli poleceń XML
Tabeli poleceń XML (*vsct*) pliku w tym artykule opisano układ i wygląd elementów polecenia dla pakietu VSPackage. Polecenie elementy obejmują przyciski, pola kombi, menu, paski narzędzi i grup elementów polecenia. W tym artykule opisano XML pliki tabeli poleceń, jak wpływają na elementy polecenia i menu oraz jak je utworzyć.

## <a name="commands-menus-groups-and-the-vsct-file"></a>Polecenia, menu, grup i pliku vsct
 *Vsct* pliki są zorganizowane wokół polecenia, menu i grup poleceń. Tagi XML w *vsct* pliku reprezentują każdego z tych elementów, oraz innych skojarzonych elementów, takich jak przyciski poleceń, położenie polecenia i map bitowych.

 Podczas tworzenia nowego pakietu VSPackage, uruchamiając [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] szablonu pakietu szablon generuje *vsct* pliku niezbędne dla polecenia menu, okna narzędzi lub niestandardowy edytor, w zależności od wyborów. To *vsct* następnie można zmodyfikować plik, aby spełniać wymagania określonego pakietu VSPackage. Przykłady sposobu modyfikowania *vsct* plików, zobacz [rozszerzenia menu i poleceń](../../extensibility/extending-menus-and-commands.md).

 Aby utworzyć nowy, pusty *vsct* plików, zobacz [porady: tworzenie *vsct* pliku](../../extensibility/internals/how-to-create-a-dot-vsct-file.md). Po utworzeniu dodać elementy, atrybuty i wartości XML do pliku do opisywania układu elementu polecenia. Aby uzyskać szczegółowe schematu XML, zobacz [odwołanie do schematu VSCT XML](../../extensibility/vsct-xml-schema-reference.md).

## <a name="differences-between-ctc-and-vsct-files"></a>Różnice między plikami .ctc i vsct
 Gdy znaczenie za XML tagów w *vsct* pliku są takie same jak te znaczniki w obecnie przestarzałe *.ctc* format pliku jest nieco inna ich implementacji:

-   Nowy  **\<extern >** tag jest, gdzie możesz odwoływać się do innych *.h* pliki, które mają być skompilowane, takie jak te pliki dla [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] paska narzędzi.

-   Gdy *vsct* pliki pomocy technicznej **/ include** instrukcji, jako *.ctc* plików, ale także nową  **\<zaimportować >** element. Różnica polega na tym, **/ include** wiąże *wszystkie* informacji, gdy  **\<zaimportować >** wiąże tylko nazwy.

-   Gdy *.ctc* plików wymaga pliku nagłówka, w której definiujesz swoje dyrektywy preprocesora, jedna nie jest wymagane dla *vsct* plików. Zamiast tego należy umieścić swoje dyrektywy w tabeli symboli znajduje się w  **\<Symbol >** elementów znajdujących się w dolnej części *vsct* pliku.

-   *vsct* funkcji pliki  **\<adnotacja >** znacznik, który umożliwia osadzanie wszelkie informacje, które lubisz, takie jak informacje o lub nawet obrazy.

-   Wartości są przechowywane jako atrybuty w elemencie.

-   Flag poleceń mogą być przechowywane osobno lub skumulowany.  Funkcja IntelliSense, jednak nie działa na flag skumulowany poleceń. Aby uzyskać więcej informacji na temat flag poleceń, zobacz [elementu CommandFlag](../../extensibility/command-flag-element.md).

-   Można określić wiele typów, takie jak podział listy rozwijane, combos itp.

-   Identyfikatory GUID nie sprawdzania poprawności.

-   Każdy element interfejsu użytkownika ma ciąg, który reprezentuje tekst, który jest wyświetlany z nim.

-   Element nadrzędny jest opcjonalne. W przypadku pominięcia wartości *grupy nieznany* jest używany.

-   *Ikonę* argument jest opcjonalny.

-   Mapa bitowa sekcji: w tej sekcji jest taka sama, jak w *.ctc* pliku, z tą różnicą, że można teraz określić nazwę pliku, za pośrednictwem Href, który będzie pobierany w przez *vsct.exe* kompilatora w czasie kompilacji.

-   ResID: Starych map bitowych zasobu, identyfikator może być używane i nadal działa tak samo, jak w *.ctc* plików.

-   HRef: Nową metodę, która pozwala określić nazwę pliku zasobu mapy bitowej. Przyjęto założenie, że wszystkie są używane, dzięki czemu można pominąć używanej sekcji. Kompilator wyszuka najpierw zasoby lokalne dla pliku, a następnie netto udziałów, a wszelkie zasoby zdefiniowane przez **/I** przełącznika.

-   Powiązanie klawiszy: Nie masz już do określenia emulator. Jeśli określono, kompilator zakłada, że edytor i emulatora są takie same.

-   Keychord: Keychord został porzucony. Nowy format jest *klucz1, Mod1, klucz2, Mod2*.  Można określić znak, szesnastkowo lub VK stałą.
       
Nowy kompilator *vsct.exe*, kompiluje zarówno *.ctc* i *vsct* plików. Stary *ctc.exe* kompilatora, jednak nie rozpoznaje i skompilować *vsct* plików.

Możesz użyć *vsct.exe* kompilator, aby przekonwertować istniejącą *.cto* mezzanine do *vsct* pliku. Aby uzyskać więcej informacji, zobacz [porady: Tworzenie pliku vsct z istniejącego pliku .cto](../../extensibility/internals/how-to-create-a-dot-vsct-file.md#how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file).

## <a name="the-vsct-file-elements"></a>Elementy pliku vsct
 Tabeli poleceń ma następujące hierarchii i elementy:

 [CommandTable, element](../../extensibility/commandtable-element.md): reprezentuje wszystkie polecenia, grupy menu i menu skojarzone z pakietu VSPackage.

 [Extern, element](../../extensibility/extern-element.md): odwołuje się do plików zewnętrznych .h, które mają do scalenia *vsct* pliku.

 [Umieść element](../../extensibility/include-element.md): odwołuje się do żadnych plików dodatkowych nagłówków (.h) do skompilowania wraz z Twojej *vsct* pliku. A *vsct* plik może zawierać *.h* pliki zawierające stałe, które określają polecenia, grupy menu i menu, które zapewnia IDE lub innego pakietu VSPackage.

 [Commands, element](../../extensibility/commands-element.md): reprezentuje wszystkie pojedynczych poleceń, które mogą być wykonywane. Każde polecenie ma następujących elementów podrzędnych cztery:

 [Element menu](../../extensibility/menus-element.md): reprezentuje wszystkie menu i paski narzędzi pakietu VSPackage. Menu są kontenerami dla grupy poleceń.

 [Element grupy](../../extensibility/groups-element.md): reprezentuje wszystkie grupy w pakietu VSPackage. Grupy są kolekcjami pojedynczych poleceń.

 [Buttons, element](../../extensibility/buttons-element.md): reprezentuje wszystkie przyciski poleceń i elementów menu w pakietu VSPackage. Przyciski są visual formanty, które mogą być skojarzone z poleceniami.

 [Bitmaps, element](../../extensibility/bitmaps-element.md): reprezentuje wszystkie mapy bitowe dla wszystkich przycisków z pakietu VSPackage. Mapy bitowe mają rozmiar obrazów wyświetlanych obok lub przycisków poleceń, w zależności od kontekstu.

 [CommandPlacements, element](../../extensibility/commandplacements-element.md): Określa dodatkowe lokalizacje, w której poszczególne polecenia powinien znajdować się w menu Twojego pakietu VSPackage.

 [VisibilityConstraints, element](../../extensibility/visibilityconstraints-element.md): Określa, czy polecenie wyświetla na wszystkich czas lub tylko w niektórych kontekstach, np. gdy zostanie wyświetlona określonego okna dialogowego lub okna. Menu i poleceń, które mają wartość dla tego elementu spowoduje wyświetlenie tylko wtedy, gdy określony kontekst jest aktywny. Zachowanie domyślne jest do wyświetlenia polecenia przez cały czas.

 [KeyBindings, element](../../extensibility/keybindings-element.md): Określa wszelkie powiązań klawiszy dla polecenia. Oznacza to, co najmniej jeden kombinacji klawiszy, które muszą zostać naciśnięte w celu wykonania tego polecenia, takie jak **Ctrl**+**S**.

 [UsedCommands, element](../../extensibility/usedcommands-element.md): informuje o [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] środowiska, mimo że określone polecenie jest implementowany przez inny kod, gdy bieżącego pakietu VSPackage jest aktywny, zapewnia wykonania polecenia.

 [Symbols, element](../../extensibility/symbols-element.md): zawiera nazwy symboli i identyfikatory GUID dla wszystkich poleceń w pakiecie.

## <a name="vsct-file-design-guidelines"></a>wytyczne dotyczące projektowania pliku vsct
 Aby pomyślnie projektowania *vsct* plików, należy przestrzegać następujących wytycznych.

-   Polecenia można umieścić tylko w grupach, grup, które można umieścić tylko w menu i menu można umieścić tylko w grupach. W środowisku IDE programu grupy są wyświetlane tylko menu i poleceń nie jest.

-   Podmenu nie można przypisać bezpośrednio do menu, ale muszą być przypisane do grupy, która z kolei jest przypisany do menu.

-   Polecenia, podmenu i grup można przypisać do jednej grupy element nadrzędny lub menu przy użyciu pola nadrzędnego ich definiujące dyrektywy.

-   Organizowanie tabeli polecenia wyłącznie za pośrednictwem pola nadrzędnego w dyrektywach ma znaczące ograniczenia. Dyrektywy definiujące obiekty, które może potrwać argument tylko jedną jednostkę nadrzędną.

-   Ponowne użycie poleceń, grup lub podmenu wymagane jest użycie nowej dyrektywy, aby utworzyć nowe wystąpienie obiektu za pomocą własnego `GUID:ID` pary.

-   Każdy `GUID:ID` pary muszą być unikatowe. Ponowne użycie polecenia, który na przykład został umieszczony w menu, pasek narzędzi lub menu kontekstowego, jest obsługiwane przez <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejsu.

-   Polecenia i podmenu również można przypisać do wielu grup i grup, które można przypisać do wielu menu przy użyciu [Commands, element](../../extensibility/commands-element.md).

## <a name="vsct-file-notes"></a>informacje o pliku vsct
 Jeśli wprowadzisz zmiany *vsct* pliku po zarówno skompilować go i umieść go w macierzystym satelitarną bibliotekę DLL, należy uruchomić **/nosetupvstemplates/Setup devenv.exe**. Wykonując tak wymusza zasobów pakietu VSPackage, określone w doświadczalnych rejestr w celu należy przeczytać i wewnętrznej bazy danych, który opisuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] odbudowania.

 Podczas tworzenia aplikacji możliwe jest dla wielu projektów pakietu VSPackage zostać utworzona i zarejestrowana w gałęzi rejestru eksperymentalnych, który może prowadzić do mylące nieładu w IDE. Aby rozwiązać ten problem, możesz zresetować eksperymentalne gałęzi do domyślnych ustawień do usuwania wszystkich zarejestrowanych pakietów VSPackage i wszelkie zmiany, które mogły zostać wprowadzone do środowiska IDE. Aby zresetować eksperymentalne hive, narzędzie CreateExpInstance.exe dostarczanego z Visual Studio SDK. Można znaleźć na stronie:

 *% PROGRAMFILES (x 86) %\Visual Studio\\\<wersji > SDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe*

 Uruchom narzędzie przy użyciu polecenia **/reset CreateExpInstance**. Należy pamiętać, że to narzędzie spowoduje usunięcie z doświadczalnych hive wszystkie zarejestrowane, nie jest zainstalowane przy użyciu pakietów VSPackage [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="see-also"></a>Zobacz także
 [Rozszerzenie menu i poleceń](../../extensibility/extending-menus-and-commands.md)