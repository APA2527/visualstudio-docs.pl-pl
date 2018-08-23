---
title: Ogłoszenie właściwość okno wyboru śledzenia | Dokumentacja firmy Microsoft
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
- editors [Visual Studio SDK], property pages support
- property pages, tracking selection
- Properties window, tracking selection
- selection, tracking
- editors [Visual Studio SDK], Properties window support
ms.assetid: a7536f82-afd7-4894-9a60-84307fb92b7e
caps.latest.revision: 13
manager: douge
ms.openlocfilehash: bb2f2ceb7ed7faa3165f2346a0e0d14de1371166
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679610"
---
# <a name="announcing-property-window-selection-tracking"></a>Ogłoszenie wybór okna właściwości śledzenia
Jeśli chcesz pracować z **właściwości** okna lub **właściwość** strony, na przykład formularz, tekst lub zaznaczenia, dla którego chcesz wyświetlić właściwości, należy zastosować pełną wiedzy na temat możesz koordynowanie zaznaczenia. Na przykład musisz wiedzieć, czy masz zaznaczenia jednego lub wiele zaznaczeń. Następnie należy poinformować o danego typu wyboru (jednego lub wielu) do środowiska IDE, za pomocą <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> interfejsu. Ten interfejs zapewnia informacje wymagane przez **właściwości** okna.  
  
### <a name="to-announce-selection-to-the-environment"></a>Ogłaszamy wyboru do środowiska  
  
1.  Wywołaj `QueryInterface` dla <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>.  
  
    1.  Aby to zrobić, należy użyć wskaźnika witryny, przekazywane do widoku podczas jego tworzenia.  
  
    2.  Wywołaj `QueryService` z widoku dla `SID_STrackSelection` usługi.  
  
         Zwraca wskaźnik do <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
2.  Wywołaj <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> metoda za każdym razem, gdy zmieni się zaznaczenie i przekazać wskaźnik do obiektu, który implementuje <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.  
  
     Wybór obiektu kontenera można używać jednego lub wielu zaznaczeń i zawiera informacje o zaznaczeniu w `IDispatch` obiektu. Wywoływanie <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> metoda powiadamia **właściwości** okna, że zaznaczenie zostało zmienione. **Właściwości** okno następnie używa obiektów na <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> ustalenie, czy wystąpiły jedną lub wiele zaznaczeń i jakie są opcje rzeczywistego obiektu.  
  
     W przypadku określenia wielu zaznaczenia, a następnie **właściwości** okna znajduje przecięcia właściwości wspólne dla obiektów. Jeśli określisz pojedynczy obiekt zaznaczenia, a następnie **właściwości** oknie, zostaną wyświetlone wszystkie właściwości w jeden obiekt.  
  
## <a name="see-also"></a>Zobacz też  
 [Rozszerzanie właściwości](../extensibility/internals/extending-properties.md)   
 [Strony właściwości](../extensibility/internals/property-pages.md)