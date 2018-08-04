---
title: Polecenie Projekt | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands
- commands, implementation
ms.assetid: 097108c3-f758-4b87-89d6-b32d12d9041a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 09792f951b0cc77d2087904b1dcebc1c9b3b6a06
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39513062"
---
# <a name="command-design"></a>Projektowanie poleceń
Dodając polecenie do VSPackage, należy określić, gdzie jest wyświetlane, gdy jest dostępna i jak ma być obsługiwane.  
  
## <a name="define-commands"></a>Zdefiniuj polecenia  
 Aby zdefiniować nowe polecenia, należy dołączyć tabeli poleceń programu Visual Studio (*vsct*) plik w projekcie pakietu VSPackage. Jeśli utworzono pakietu VSPackage za pomocą szablonu pakietu Visual Studio, projekt zawiera jeden z tych plików. Aby uzyskać więcej informacji, zobacz [pliki tabeli (vsct) polecenia programu Visual Studio](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 Program Visual Studio łączy wszystkie *vsct* plików znajduje tak, aby możliwe było wyświetlanie poleceń. Ponieważ te pliki różnią się od pakietu VSPackage binarne, Visual Studio nie ma załadowanie pakietu można znaleźć polecenia. Aby uzyskać więcej informacji, zobacz [VSPackages jak dodać elementy interfejsu użytkownika](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Program Visual Studio używa <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> rejestracji atrybut do definiowania zasobów menu i poleceń. Aby uzyskać więcej informacji, zobacz [implementacja poleceń](../../extensibility/internals/command-implementation.md).  
  
 Polecenia można zmienić w czasie wykonywania na wiele różnych sposobów. Można je wyświetlane lub ukryte, włączone lub wyłączone. Mogą wyświetlić inny tekst lub ikony lub zawierać różne wartości. Bardzo duże możliwości dostosowania mogą być wykonywane przed Visual Studio ładuje Twojego pakietu VSPackage. Aby uzyskać więcej informacji, zobacz [VSPackages jak dodać elementy interfejsu użytkownika](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
## <a name="command-handlers"></a>Programy obsługi poleceń  
 Podczas tworzenia polecenia należy podać program obsługi zdarzeń w celu wykonania tego polecenia. Jeśli użytkownik wybierze polecenie, należy odpowiednio kierowana. Routing polecenie oznacza wysłaniem go do poprawne pakietu VSPackage, aby włączyć lub ją wyłączyć, ukryć lub wyświetlić je i wykonaj go, jeśli użytkownik zdecyduje to zrobić. Aby uzyskać więcej informacji, zobacz [algorytm routingu poleceń](../../extensibility/internals/command-routing-algorithm.md).  
  
## <a name="visual-studio-command-environment"></a>Środowisko polecenia w usłudze Visual Studio  
 Program Visual Studio może obsługiwać dowolną liczbę pakietów VSPackage, a każdy może współtworzyć zawartość swój własny zestaw poleceń. Środowisko zawiera tylko polecenia, które są odpowiednie dla bieżącego zadania. Aby uzyskać więcej informacji, zobacz [polecenia dostępności](../../extensibility/internals/command-availability.md) i [wybór obiektów kontekstu](../../extensibility/internals/selection-context-objects.md).  
  
 Pakietu VSPackage, który definiuje nowe polecenia, menu, paski narzędzi lub menu skrótów informacje jego polecenia do programu Visual Studio w momencie instalacji za pośrednictwem wpisów rejestru dodawanych odwoływać się do zasobów w zestawach natywnego, zarządzanego. Każdy zasób, następnie odwołuje się do zasobu danych binarnych (*.cto*) plik, który jest generowany, gdy kompilujesz tabeli poleceń programu Visual Studio (*vsct*) pliku. Dzięki temu program Visual Studio zapewniają zestawy poleceń scalone, menu i paski narzędzi bez konieczności ładowania każdego zainstalowanego pakietu VSPackage.  
  
### <a name="command-organization"></a>Polecenie organizacji  
 Środowisko umieszcza polecenia według grupy, priorytetu i menu.  
  
-   Grupy są logicznymi kolekcjami powiązane polecenia, na przykład, **Wytnij**, **kopiowania**, i **Wklej** grupy poleceń. Grupy są poleceniami, które są wyświetlane w menu.  
  
-   Priorytet określa kolejność wyświetlania pojedynczych poleceń w grupie menu.  
  
-   Menu działają jak kontenery dla grupy.  
  
 Środowisko powoduje wstępne definiowanie niektórych poleceń, grup i menu. Aby uzyskać więcej informacji, zobacz [domyślne położenie poleceń, grup i narzędzi](../../extensibility/internals/default-command-group-and-toolbar-placement.md).  
  
 Polecenia można przypisać do grupy podstawowej. Grupa podstawowa określa położenie polecenia w strukturze menu głównego, a w **Dostosuj** okno dialogowe. Polecenie może znajdować się w wielu grupach; na przykład polecenie może być menu głównego, w menu skrótów i na pasku narzędzi. Aby uzyskać więcej informacji, zobacz [VSPackages jak dodać elementy interfejsu użytkownika](../../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
### <a name="command-routing"></a>Routing poleceń  
 Proces wywoływania i routing poleceń dla pakietów VSPackage różni się od proces wywoływania metod dla wystąpienia obiektu.  
  
 Środowisko kieruje polecenia sekwencyjnie od kontekst najbardziej polecenia (local), który jest oparty na bieżącym zaznaczeniu, prowadzące kontekst (globalna). Pierwszy kontekst, który jest w stanie wykonać polecenia jest to, która je obsługuje. Aby uzyskać więcej informacji, zobacz [algorytm routingu poleceń](../../extensibility/internals/command-routing-algorithm.md).  
  
 W większości przypadków środowiska obsługi poleceń przy użyciu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejsu. Ponieważ schemat routingu poleceń umożliwia wiele różnych obiektów, do obsługi poleceń, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> może być implementowany przez dowolną liczbę obiektów; te obejmują kontrolek ActiveX firmy Microsoft, implementacje widoku okna, obiektów dokumentu, hierarchii projektu i pakietu VSPackage same obiekty (w przypadku polecenia globalne). W niektórych przypadkach specjalistyczne, na przykład routingu poleceń w hierarchii, <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> należy zaimplementować interfejs.  
  
## <a name="related-topics"></a>Tematy pokrewne  
  
|Tytuł|Opis|  
|-----------|-----------------|  
|[Implementacja poleceń](../../extensibility/internals/command-implementation.md)|Opisuje sposób implementacji poleceń w VSPackage.|  
|[Dostępność poleceń](../../extensibility/internals/command-availability.md)|W tym artykule opisano, jak kontekstu programu Visual Studio Określa, jakie polecenia są dostępne.|  
|[Algorytm routingu poleceń](../../extensibility/internals/command-routing-algorithm.md)|W tym artykule opisano, jak Visual Studio polecenie routingu w uzyskaniu poleceń, które mają być obsługiwane przez różne pakietów VSPackage.|  
|[Wskazówki dotyczące umieszczania poleceń](../../extensibility/internals/command-placement-guidelines.md)|Sugeruje położenie poleceń w środowisku Visual Studio.|  
|[Jak dodać elementy interfejsu użytkownika w pakietach VSPackage](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)|W tym artykule opisano, jak pakietów VSPackage najlepiej mogą korzystać z architekturą polecenia programu Visual Studio.|  
|[Domyślne położenie poleceń, grup i narzędzi](../../extensibility/internals/default-command-group-and-toolbar-placement.md)|W tym artykule opisano, jak pakietów VSPackage najlepiej użyć polecenia, które znajdują się w programie Visual Studio.|  
|[Zarządzanie pakietami VSPackage](../../extensibility/managing-vspackages.md)|W tym artykule opisano, jak Visual Studio ładuje pakietów VSPackage.|  
|[Pliki tabeli (vsct) polecenia programu Visual Studio](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)|Informacje na temat opartych na języku XML *vsct* pliki, które są używane do opisywania układ i wygląd poleceń w pakietach VSPackage.|