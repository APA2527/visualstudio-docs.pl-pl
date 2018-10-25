---
title: MenuCommands programu Vs. OleMenuCommands | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- commands, creating in VSPackages
- command buttons, creating and placing
- menus, creating commands
ms.assetid: 553d5e07-3e19-4aba-b490-6c7dd05fd82e
caps.latest.revision: 46
manager: douge
ms.openlocfilehash: 3b548a43cabcb097250411c3475f47774c840511
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49911918"
---
# <a name="menucommands-vs-olemenucommands"></a>MenuCommands programu Vs. OleMenuCommands
Można utworzyć polecenia menu pochodząca z <xref:System.ComponentModel.Design.MenuCommand> lub <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiektu i impementling procedur obsługi zdarzeń właściwe. W większości przypadków można użyć <xref:System.ComponentModel.Design.MenuCommand>, zgodnie z szablonu projektu pakietu VSPackage, ale może od czasu do czasu może być konieczne użycie <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>.  
  
 Można ich używać poleceń, że udostępnia pakietu VSPackage środowiska IDE programu musi być widoczne i włączone przed użytkownikiem. Po utworzeniu polecenia w pliku vsct za pomocą szablonu projektu pakietu Visual Studio są widoczne i włączone domyślnie. Ustawienie niektórych flag poleceń, takich jak `DynamicItemStart`, można zmienić domyślne zachowanie. Widoczność, włączony stan i inne właściwości polecenia można także zmienić w kodzie w czasie wykonywania, uzyskując dostęp do <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiekt, który jest skojarzony z poleceniem.  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 Aby skorzystać z tego przewodnika, należy zainstalować program Visual Studio SDK. Aby uzyskać więcej informacji, zobacz [programu Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="template-locations-for-the-visual-studio-package-template"></a>Lokalizacje szablonów dla szablonu pakietu programu Visual Studio  
 Można znaleźć szablonu pakiet rozszerzeń Visual Studio w **nowy projekt** , okno dialogowe **języka Visual Basic / rozszerzalności**, **C# / rozszerzalności**, lub **innych Typy projektów / rozszerzalności**.  
  
## <a name="creating-a-command"></a>Tworzenie polecenia  
 Wszystkie polecenia, grup poleceń, menu, paski narzędzi i okien narzędzi są definiowane w pliku vsct. Aby uzyskać więcej informacji, zobacz [tabeli poleceń w usłudze Visual Studio (. Pliki Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 W przypadku tworzenia za pomocą szablonu pakietu VSPackage, wybierz **polecenia Menu** Tworzenie pliku vsct i definiowanie polecenia menu domyślne. Aby uzyskać więcej informacji, zobacz [Tworzenie rozszerzenia za pomocą polecenia Menu](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
#### <a name="to-add-a-command-to-the-ide"></a>Aby dodać polecenie do środowiska IDE  
  
1. Otwórz plik vsct.  
  
2. W `Symbols` sekcji, Znajdź [GuidSymbol](../extensibility/guidsymbol-element.md) element, który zawiera grupy i polecenia.  
  
3. Tworzenie [IDSymbol](../extensibility/idsymbol-element.md) elementu dla każdego menu, grupy lub polecenia, którą chcesz dodać, jak pokazano w poniższym przykładzie.  
  
   ```xml
   <GuidSymbol name="guidButtonGroupCmdSet" value="{f69209e9-975a-4543-821d-1f4a2c52d737}">
     <IDSymbol name="MyMenuGroup" value="0x1020" />
     <IDSymbol name="cmdidMyCommand" value="0x0100" />
   </GuidSymbol>
   ```
      
    `name` Atrybuty `GuidSymbol` i `IDSymbol` elementy Podaj pary GUID:ID dla każdego nowego menu, grupy lub polecenia. `guid` Reprezentuje zestaw poleceń, która jest zdefiniowana dla Twojego pakietu VSPackage. Można zdefiniować wiele zestawów polecenia. Każda para GUID:ID musi być unikatowa.  
  
4. W [przyciski](../extensibility/buttons-element.md) sekcji, Utwórz [przycisk](../extensibility/button-element.md) elementu, aby zdefiniować polecenia, jak pokazano w poniższym przykładzie.  
  
   ```xml
   <Button guid="guidButtonGroupCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
     <Parent guid="guidButtonGroupCmdSet" id="MyMenuGroup" />
     <Icon guid="guidImages" id="bmpPic1" />
     <Strings>
       <CommandName>cmdidMyCommand</CommandName>
       <ButtonText>My Command name</ButtonText>
     </Strings>
   </Button>
   ``` 
     
   1.  Ustaw `guid` i `id` pól do dopasowania GUID:ID nowego polecenia.  
  
   2.  Ustaw `priority` atrybutu.  
  
        `priority` Atrybut jest używany przez vsct do określenia lokalizacji przycisku, między innymi obiektami w jego grupie nadrzędnej.  
  
        Polecenia, które mają niższe wartości priorytetu są wyświetlane powyżej lub po lewej stronie, polecenia, które mają wyższe wartości priorytetu. Priorytet zduplikowane wartości są dozwolone, ale względne położenie poleceń, które mają taki sam priorytet, jest określana przez kolejność, w którym pakietów VSPackage są przetwarzane w czasie wykonywania, a tej kolejności nie może być wcześniej.  
  
        Pominięcie `priority` atrybut ustawia dla niej wartość 0.  
  
   3.  Ustaw `type` atrybutu. W większości przypadków, jego wartość będzie `"Button"`. Opisy innych typach przycisków prawidłowe można znaleźć [Button Element](../extensibility/button-element.md).  
  
5. W definicji przycisku Utwórz [ciągi](../extensibility/strings-element.md) element, który zawiera [ButtonText](../extensibility/buttontext-element.md) element, aby zawierały nazwę menu, która jest wyświetlana w IDE, a [CommandName](../extensibility/commandname-element.md) element, aby zawierały nazwę polecenia, który umożliwia dostęp do menu w **polecenia** okna.  
  
    Jeśli ciąg tekstowy przycisk zawiera znak "&", użytkownik może otworzyć menu, naciskając klawisze ALT plus oznacza bezpośrednio następuje znak "&".  
  
    Dodawanie `Tooltip` spowoduje, że element zawarty tekst do są wyświetlane, gdy użytkownik zatrzyma wskaźnik przycisku.  
  
6. Dodaj [ikonę](../extensibility/icon-element.md) elementu, aby wybrać ikonę, która, jeśli mają być wyświetlane za pomocą polecenia. Ikony są wymagane dla przycisków na paskach narzędzi, ale nie dla elementów menu. `guid` i `id` z `Icon` element musi być zgodne z nazwami [mapy bitowej](../extensibility/bitmap-element.md) elementu zdefiniowanego w `Bitmaps` sekcji.  
  
7. Dodaj polecenie flagi, zgodnie z potrzebami zmienić wygląd i zachowanie przycisku. Aby to zrobić, Dodaj [CommandFlag](../extensibility/command-flag-element.md) elementu w definicji menu.  
  
8. Ustaw grupę nadrzędną polecenia. Grupa nadrzędna może być grupy, którą tworzysz, grupy z innym pakietem lub grupą z poziomu środowiska IDE. Na przykład, aby dodać polecenie do paska narzędzi edycji programu Visual Studio obok **komentarz** i **Usuń komentarz** przyciski, ustaw guidStdEditor:IDG_VS_EDITTOOLBAR_COMMENT obiektu nadrzędnego. Jeśli element nadrzędny jest grupą zdefiniowanych przez użytkownika, należy elementem podrzędnym elementu menu, pasek narzędzi lub okna narzędzi, który pojawia się w środowisku IDE.  
  
    To zrobić na dwa sposoby, w zależności od projektu:  
  
   -   W `Button` elementu, Utwórz [nadrzędnego](../extensibility/parent-element.md) element i ustaw jego `guid` i `id` pola Identyfikator Guid i identyfikator grupy, która będzie obsługiwać polecenia, znany także jako *głównej grupy*.  
  
        W poniższym przykładzie zdefiniowano polecenia, która będzie wyświetlana w menu zdefiniowanych przez użytkownika.  
  
       ```xml
       <Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">
         <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />
         <Icon guid="guidImages" id="bmpPic1" />
         <Strings>
           <CommandName>cmdidTestCommand</CommandName>
           <ButtonText>Test Command</ButtonText>
             </Strings>
       </Button>
       ```
      
   -   Możesz pominąć `Parent` elementu, jeśli polecenie ma znajdować się za pomocą polecenia umieszczania. Tworzenie [CommandPlacements](../extensibility/commandplacements-element.md) przed elementem `Symbols` sekcji i Dodaj [CommandPlacement](../extensibility/commandplacement-element.md) element, który ma `guid` i `id` polecenia `priority`i element nadrzędny, jak pokazano w poniższym przykładzie.  
  
   ```xml
   <CommandPlacements>
     <CommandPlacement guid="guidButtonGroupCmdSet" id="cmdidMyCommand" priority="0x105">
       <Parent guid="guidButtonGroupCmdSet" id="MyMenuGroup" />
     </CommandPlacement>
   </CommandPlacements>
   ```
      
        Creating multiple command placements that have the same GUID:ID and have different parents causes a menu to appear in multiple locations. For more information, see [CommandPlacements](../extensibility/commandplacements-element.md) element.  
  
    Aby uzyskać więcej informacji na temat grup poleceń i element nadrzędny, zobacz [tworzenia wielokrotnego użytku, do grup przycisków](../extensibility/creating-reusable-groups-of-buttons.md).  
  
   W tym momencie polecenia będą widoczne w IDE, ale będzie miał żadne funkcje. Jeśli polecenie została utworzona przez szablon pakietu, będzie miał kliknij program obsługi, który zostanie wyświetlony komunikat domyślny.  
  
## <a name="handling-the-new-command"></a>Obsługa nowego polecenia  
 Większość używanych poleceń w kodzie zarządzanym może zostać obsłużony przez Framework zarządzane pakietu (MPF) przez kojarzenie polecenia za pomocą <xref:System.ComponentModel.Design.MenuCommand> obiektu lub <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiektu i wdrażanie jej procedury obsługi zdarzeń.  
  
 Dla kodu, który używa <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejs bezpośrednio do obsługi poleceń, musisz zaimplementować <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejsu i jej metody. Dwie najważniejsze metody są <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> i <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>.  
  
1.  Pobierz <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> wystąpienia, jak pokazano w poniższym przykładzie.  
  
     [!code-csharp[ButtonGroup#21](../snippets/csharp/VS_Snippets_VSSDK/buttongroup/cs/buttongrouppackage.cs#21)]  
  
2.  Utwórz <xref:System.ComponentModel.Design.CommandID> obiekt, który ma parametrów, identyfikator GUID i identyfikator polecenia do obsługi, jak pokazano w poniższym przykładzie.  
  
     [!code-csharp[ButtonGroup#22](../snippets/csharp/VS_Snippets_VSSDK/buttongroup/cs/buttongrouppackage.cs#22)]  
  
     Szablon pakiet rozszerzeń Visual Studio zawiera dwie kolekcje `GuidList` i `PkgCmdIDList`, do przechowywania identyfikatorów GUID i identyfikatory poleceń. Te są wypełniane automatycznie dla poleceń, które są dodawane przez szablon, ale dla poleceń, które możesz dodać ręcznie, musisz również dodać wpis identyfikator, aby `PkgCmdIdList` klasy.  
  
     Alternatywnie możesz wypełnić <xref:System.ComponentModel.Design.CommandID> obiektu za pomocą wartość nieprzetworzonego ciągu identyfikatora GUID i wartość całkowitą identyfikatora.  
  
3.  Utwórz wystąpienie albo <xref:System.ComponentModel.Design.MenuCommand> lub <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiekt, który określa metodę, która obsługuje polecenie, łącznie z <xref:System.ComponentModel.Design.CommandID>, jak pokazano w poniższym przykładzie.  
  
     [!code-csharp[ButtonGroup#23](../snippets/csharp/VS_Snippets_VSSDK/buttongroup/cs/buttongrouppackage.cs#23)]  
  
     <xref:System.ComponentModel.Design.MenuCommand> Jest odpowiednia dla statycznych poleceń. Wyświetla element menu dynamiczne wymagają QueryStatus obsługi zdarzeń. <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> Dodaje <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> zdarzenie, które występuje, gdy menu hosta polecenia jest otwarty i niektóre inne właściwości, takie jak <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Polecenia utworzone przez szablon pakietu są przekazywane, aby domyślnie <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiektu `Initialize()` metody klasy pakietu.  
  
4.  <xref:System.ComponentModel.Design.MenuCommand> Jest odpowiednia dla statycznych poleceń. Wyświetla element menu dynamiczne wymagają QueryStatus obsługi zdarzeń. <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> Dodaje <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> zdarzenie, które występuje, gdy menu hosta polecenia jest otwarty i niektóre inne właściwości, takie jak <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Polecenia utworzone przez szablon pakietu są przekazywane, aby domyślnie <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiektu `Initialize()` metody klasy pakietu. Kreator programu Visual Studio implementuje `Initialize` metody, używając `MenuCommand`. Do wyświetlania elementu menu dynamiczne, musisz zmienić tę wartość do `OleMenuCommand`, jak pokazano w następnym kroku. Co więcej Aby zmienić tekst elementu menu, należy dodać TextChanges flagę polecenia do menu przycisku polecenia w pliku vsct jak pokazano w poniższym przykładzie  
  
    ```xml
    <Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
      <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
      <Icon guid="guidImages" id="bmpPic1" />
      <CommandFlag>TextChanges</CommandFlag>
      <Strings>
        <CommandName>cmdidMyCommand</CommandName>
        <ButtonText>My Command name</ButtonText>
      </Strings>
    </Button>
    ```
      
5.  Nowe polecenie menu, aby przekazać <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> method in Class metoda <xref:System.ComponentModel.Design.IMenuCommandService> interfejsu. Jest to osiągane przez domyślny dla polecenia utworzone przez szablon pakietu, jak pokazano w poniższym przykładzie  
  
     [!code-csharp[ButtonGroup#24](../snippets/csharp/VS_Snippets_VSSDK/buttongroup/cs/buttongrouppackage.cs#24)]  
  
6.  Implementuje metody, która obsługuje polecenie.  
  
#### <a name="to-implement-querystatus"></a>Aby zaimplementować QueryStatus  
  
1. Zdarzenie QueryStatus występuje przed wyświetleniem polecenia. Dzięki temu właściwości tego polecenia można ustawić w zdarzeniu programu obsługi przed osiągnięciem przez nią użytkownika. Tylko polecenia, które są dodawane jako <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiekty mogą uzyskiwać dostęp do tej metody.  
  
    Dodaj `EventHandler` obiekt <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> zdarzenia w <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiekt, który jest tworzony do obsługi polecenia, jak pokazano w poniższym przykładzie (`menuItem` jest <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> wystąpienie).  
  
    [!code-csharp[MenuText#14](../snippets/csharp/VS_Snippets_VSSDK/menutext/cs/menutextpackage.cs#14)]
    [!code-vb[MenuText#14](../snippets/visualbasic/VS_Snippets_VSSDK/menutext/vb/menutextpackage.vb#14)]  
  
    `EventHandler` Obiekt otrzymuje nazwę metody, która jest wywoływana, gdy stan to polecenie jest wykonywane zapytanie.  
  
2. Implementuje metody obsługi stanu zapytania dla polecenia. `object` `sender` Parametru może być rzutowany <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiektu, który służy do ustawiania różne atrybuty polecenia menu, w tym tekście. W poniższej tabeli przedstawiono właściwości na <xref:System.ComponentModel.Design.MenuCommand> klasy (które klasy MPF <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> pochodzi od klasy) odpowiadające <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> flag.  
  
   |Właściwość MenuCommand|Flaga OLECMDF|  
   |--------------------------|------------------|  
   |<xref:System.ComponentModel.Design.MenuCommand.Checked%2A> = `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
   |<xref:System.ComponentModel.Design.MenuCommand.Visible%2A> = `false`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
   |<xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> = `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
  
    Aby zmienić tekst polecenia menu, użyj <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A> właściwość <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> obiektu, jak pokazano w poniższym przykładzie.  
  
    [!code-csharp[MenuText#11](../snippets/csharp/VS_Snippets_VSSDK/menutext/cs/menutextpackage.cs#11)]
    [!code-vb[MenuText#11](../snippets/visualbasic/VS_Snippets_VSSDK/menutext/vb/menutextpackage.vb#11)]  
  
   MPF automatycznie obsługuje przypadek grupy Nieobsługiwana lub nieznana. O ile nie została dodana do polecenia <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> przy użyciu <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> metoda, polecenie nie jest obsługiwana.  
  
### <a name="handling-commands-by-using-the-iolecommandtarget-interface"></a>Obsługa poleceń przy użyciu iolecommandtarget — interfejs  
 Dla kodu, który używa <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejs bezpośrednio, pakietu VSPackage należy zaimplementować obu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> i <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejsu. Jeśli pakietu VSPackage implementuje hierarchii projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> i <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> interfejsu powinny być zrealizowane w zamian.  
  
 Zarówno <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> i <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody zostały zaprojektowane do odbierania zestawu pojedynczego polecenia `GUID` oraz tablicę identyfikatorów poleceń jako dane wejściowe. Zaleca się, że pakietów VSPackage w pełni obsługuje tę koncepcję wiele identyfikatorów w jednym wywołaniu. Jednak tak długo, jak pakietu VSPackage nie jest wywoływany z innych pakietów VSPackage, można założyć tablicy polecenia zawiera tylko jeden identyfikator polecenia, ponieważ <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> i <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody są wykonywane w dobrze zdefiniowanej kolejności. Aby uzyskać więcej informacji na temat routingu, zobacz [Routing poleceń w pakietach VSPackage](../extensibility/internals/command-routing-in-vspackages.md).  
  
 Dla kodu, który używa <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejs bezpośrednio do obsługi poleceń, musisz zaimplementować <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody w VSPackage w następujący sposób w celu obsługi poleceń.  
  
##### <a name="to-implement-the-querystatus-method"></a>Aby wdrożyć metodę QueryStatus  
  
1. Zwróć <xref:Microsoft.VisualStudio.VSConstants.S_OK> dla prawidłowych poleceń.  
  
2. Ustaw `cmdf` elementu `prgCmds` parametru.  
  
    Wartość `cmdf` element jest połączeniem logicznym wartości z <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> wyliczenia, połączone za pomocą operatora logicznego OR (`|`) — operator.  
  
    Użyj odpowiedniego wyliczenia, na podstawie stanu polecenia:  
  
   - Jeśli polecenie jest obsługiwane:  
  
      `prgCmds[0].cmdf = OLECMDF_SUPPORTED;`  
  
   - Jeśli polecenie ma być niewidoczna w tej chwili:  
  
      `prgCmds[0].cmdf |= OLECMDF_INVISIBLE;`  
  
   - Jeśli polecenie jest przełączona w i prawdopodobnie została kliknięta:  
  
      `prgCmds[0].cmdf |= OLECMDF_LATCHED;`  
  
      W przypadku przetwarzania poleceń, które znajdują się w menu typu `MenuControllerLatched`, pierwsze polecenie, która jest oznaczona za `OLECMDF_LATCHED` flaga jest domyślnego polecenia, która jest wyświetlana w menu rozruchu. Aby uzyskać więcej informacji na temat `MenuController` menu, zobacz [Menu Element](../extensibility/menu-element.md).  
  
   - Jeśli polecenie jest obecnie włączona:  
  
      `prgCmds[0].cmdf |= OLECMDF_ENABLED;`  
  
   - Jeśli polecenie jest częścią menu skrótów i jest domyślnie ukryty:  
  
      `prgCmds[0] cmdf |= OLECMDF_DEFHIDEONCTXMENU`  
  
   - Jeśli polecenie używa `TEXTCHANGES` Flaga, ustaw `rgwz` elementu `pCmdText` parametru na nowy tekst polecenia i zestawu `cwActual` elementu `pCmdText` parametru, aby rozmiar ciągu polecenia.  
  
     Dla warunków błędu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody musi obsługiwać następujące przypadki błędów:  
  
   - Jeśli identyfikator GUID jest nieznany lub nie jest obsługiwany, zwrócony `OLECMDERR_E_UNKNOWNGROUP`.  
  
   - Jeśli jest znany identyfikator GUID, ale identyfikator polecenia jest nieznany lub nie jest obsługiwany, zwrócony `OLECMDERR_E_NOTSUPPORTED`.  
  
   Implementacja pakietu VSPackage <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody musi także zwracać konkretnych kodach błędów, w zależności od tego, czy polecenie jest obsługiwane i tego, czy polecenie zostało obsłużone pomyślnie.  
  
##### <a name="to-implement-the-exec-method"></a>Aby zaimplementować Exec — metoda  
  
-   Jeśli polecenie `GUID` jest nieznany, zwracają `OLECMDERR_E_UNKNOWNGROUP`.  
  
-   Jeśli `GUID` jest znane, ale polecenie identyfikator jest nieznany, zwróć `OLECMDERR_E_NOTSUPPORTED`.  
  
-   Jeśli `GUID` i polecenia identyfikator zgodny z pary GUID:ID, który jest używany przez polecenia w pliku vsct, należy wykonać kod, który jest skojarzony z polecenia i zwrócenia <xref:Microsoft.VisualStudio.VSConstants.S_OK>.  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do schematu VSCT XML](../extensibility/vsct-xml-schema-reference.md)   
 [Rozszerzanie menu i poleceń](../extensibility/extending-menus-and-commands.md)