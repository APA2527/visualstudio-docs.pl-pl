---
title: Odwołanie do schematu VSCT XML | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio command table configuration files (VSCT), XML schema
- VSCT XML schema elements
ms.assetid: 49e7efae-e713-4762-a824-96fdaf92cdc9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 73267319733dd6e31b21a0a47796f9766250bb89
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586837"
---
# <a name="vsct-xml-schema-reference"></a>Odwołanie do schematu VSCT XML
Zapewnia tabelę polecenia tabeli kompilatora elementów schematu, dozwolone podrzędnych elementów i atrybutów dla każdego.  
  
 Plik konfiguracji (vsct) tabeli polecenia opartego na języku XML definiuje elementy polecenia, które zapewnia pakietu VSPackage do zintegrowanego środowiska programistycznego (IDE). Należą do nich elementy menu, menu, paski narzędzi i pola kombi.  
  
> [!NOTE]
>  Kompilatora VSCT można uruchomić preprocesora do pliku vsct. Ponieważ jest to zazwyczaj zawiera preprocesora, można zdefiniować C++ i makra, które mają tej samej składni, który jest używany w plikach języka C++. Przykłady tego znajdują się w vsct pliku, który **nowy projekt** Kreator tworzy dla projektu pakietu VSPackage.  
  
## <a name="optional-elements"></a>Elementy opcjonalne  
 Niektóre elementy VSCT są opcjonalne. Jeśli `Parent` argument nie zostanie określony, zostanie też dorozumianych Group_Undefined:0. Jeśli `Icon` argument nie zostanie określony, zostanie też dorozumianych guidOfficeIcon:msotcidNoIcon. Po zdefiniowaniu klawisza skrótu emulacji, która jest zwykle używana, jest opcjonalne.  
  
 Elementy mapy bitowej może być osadzony w czasie kompilacji, określając lokalizację paska mapy bitowej w `href` argumentu. Usuń mapy bitowej jest kopiowane podczas scalania zamiast wyodrębniane z zasobów biblioteki DLL. Gdy `href` argument zostanie podany, `usedList` argument staje się opcjonalny, a wszystkie gniazda na pasku mapy bitowej są traktowane jako używane.  
  
 Wszystkie wartości Identyfikator GUID i identyfikator musi być zdefiniowany za pomocą nazw symbolicznych. Te nazwy mogą być określone w plikach nagłówkowych lub VSCT \<symbole > sekcji. Symbolicznych nazw musi określać elementy lokalne, wynikające z \<Include > elementy, lub odwołuje \<Extern > elementy. Nazwa symboliczna została zaimportowana z określonych w pliku nagłówka \<Extern > elementu, jeśli jest zgodna z prostego wzorzec #define wartość SYMBOL. Wartość może być inny symbol, tak długo, jak wcześniej zdefiniowanego symbolu. Identyfikator GUID definicji należy wykonać formacie OLE lub C++. Wartości Identyfikatora może być dziesiętnych lub szesnastkowych, które są poprzedzone 0 x, jak pokazano w następujących wierszach:  
  
-   {6D484634-E53D-4a2c-ADCB-55145C9362C8}  
  
-   {0x6d484634, 0xe53d, 0x4a2c, {0xad, 0xcb, 0x55, 0x14, 0x5c, 0x93, 0x62, 0xc8}}  
  
 Komentarze XML mogą być używane, ale mogą je odrzucić obustronne narzędzi graficznego interfejsu użytkownika (GUI). Zawartość \<adnotacja > elementy są gwarantowane utrzymanie niezależnie od tego, w formacie.  
  
## <a name="schema-hierarchy"></a>Hierarchia schematu  
 Pliku vsct zawiera następujące elementy główne.  
  
 [CommandTable, element](../extensibility/commandtable-element.md)  
  
 [Extern, element](../extensibility/extern-element.md)  
  
 [Umieść element](../extensibility/include-element.md)  
  
 [Define, element](../extensibility/define-element.md)  
  
 [Commands, element](../extensibility/commands-element.md)  
  
 [CommandPlacements, element](../extensibility/commandplacements-element.md)  
  
 [VisibilityConstraints, element](../extensibility/visibilityconstraints-element.md)  
  
 [KeyBindings, element](../extensibility/keybindings-element.md)  
  
 [UsedCommands, element](../extensibility/usedcommands-element.md)  
  
 [Element nadrzędny](../extensibility/parent-element.md)  
  
 [Icon, element](../extensibility/icon-element.md)  
  
 [Strings, element](../extensibility/strings-element.md)  
  
 [Command Flag, element](../extensibility/command-flag-element.md)  
  
 [Symbols, element](../extensibility/symbols-element.md)  
  
 [Atrybuty warunkowe](../extensibility/vsct-xml-schema-conditional-attributes.md)  
  
## <a name="see-also"></a>Zobacz także  
 [Jak dodać elementy interfejsu użytkownika w pakietach VSPackage](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Routing poleceń w pakietach VSPackage](../extensibility/internals/command-routing-in-vspackages.md)