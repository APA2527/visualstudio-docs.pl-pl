---
title: VisibilityItem, Element | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f0dd09d963fe28cafb611947f2c542c4b78ba39
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586264"
---
# <a name="visibilityitem-element"></a>VisibilityItem, element
`VisibilityItem` Element określa statyczne widoczności poleceń i paski narzędzi. Każdy wpis identyfikuje polecenia lub menu, a także polecenia skojarzonego kontekstu interfejsu użytkownika. Program Visual Studio wykrywa polecenia, menu i paski narzędzi i ich widoczność bez ładowanie pakietów VSPackage, który definiuje je. IDE używa <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> metodę pozwala ustalić, czy kontekst interfejsu użytkownika poleceń jest aktywny.  
  
 Po załadowaniu pakietu VSPackage programu Visual Studio oczekuje widoczność polecenie określone przez pakietu VSPackage zamiast `VisibilityItem`. Aby ustalić widoczność dla polecenia, można zaimplementować jedną <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> programu obsługi zdarzeń lub <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody, w zależności od tego, jak zostały zaimplementowane swojej dyspozycji.  
  
 Polecenie lub menu, który ma `VisibilityItem` element, który jest wyświetlany tylko wtedy, gdy aktywny jest skojarzonego kontekstu. Jednego polecenia, menu lub paska narzędzi można skojarzyć z co najmniej jeden kontekst poleceń interfejsu użytkownika, umieszczając wpis dla każdej kombinacji kontekst polecenia. Polecenie lub menu jest skojarzony z wielu kontekstach interfejs użytkownika polecenia, następnie polecenia lub menu jest widoczna gdy dowolne spośród kontekstów interfejsu użytkownika polecenie skojarzone jest aktywny.  
  
 `VisibilityItem` Elementu dotyczy tylko polecenia, menu i paski narzędzi, nie do grup. Element, który nie ma powiązanej `VisibilityItem` element jest widoczny w każdym przypadku, gdy jego nadrzędny menu jest aktywny.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|Identyfikator GUID|Wymagane. Identyfikator GUID identyfikatora polecenia identyfikator GUID/ID.|  
|identyfikator|Wymagane. Identyfikator GUID/ID identyfikator polecenia.|  
|kontekst|Wymagane. Kontekst interfejsu użytkownika, w którym polecenie jest widoczna.|  
|Warunek|Opcjonalna. Zobacz [atrybuty warunkowe](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[VisibilityConstraints, element](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints` Element określa statyczne widoczność grupy poleceń i paski narzędzi.|  
  
## <a name="remarks"></a>Uwagi  
 Standardowa kontekstów interfejsie użytkownika Visual Studio są zdefiniowane w *ścieżka instalacji programu Visual Studio SDK*\VisualStudioIntegration\Common\Inc\vsshlids.h pliku również jako <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> i <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> klasy. Bardziej kompletny zestaw kontekstów interfejsu użytkownika jest zdefiniowany w <xref:Microsoft.VisualStudio.VSConstants> klasy.  
  
## <a name="example"></a>Przykład  
  
```xml  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>Zobacz także  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [VisibilityConstraints, element](../extensibility/visibilityconstraints-element.md)   
 [Tabeli poleceń w usłudze Visual Studio (. Pliki Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)