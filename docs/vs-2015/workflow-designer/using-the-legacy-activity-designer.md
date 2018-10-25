---
title: Przy użyciu starszej wersji projektanta działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- activities, configuring
- custom activities
- Activity Designer
- child activities, adding
- activities, adding child
- activities, creating custom
ms.assetid: 2fea8a05-6e58-423d-94bf-a822b15ffb80
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: a6c8aafe9eac26080bfbf57d06c7d512d1e1e62d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49843434"
---
# <a name="using-the-legacy-activity-designer"></a>Używanie starszej wersji projektanta działań
W tym temacie opisano sposób używania projektanta działań w starszej wersji [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Podczas określania wartości za pomocą starszej wersji projektanta [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] lub [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Projektant działań umożliwia tworzenie własnych niestandardowych działań.  
  
## <a name="creating-a-custom-activity"></a>Tworzenie niestandardowego działania  
 Wykonaj następujące kroki, aby utworzyć niestandardowe działanie za pomocą projektanta działań:  
  
1. Na **projektu** menu, kliknij przycisk **Dodaj działanie**.  
  
2. Wybierz **działania** lub **działanie (z separacją kodu)** szablonu.  
  
   1.  Użyj **działania** szablonu w celu utworzenia działanie z definicją działania i kod użytkownika, w tym samym pliku kodu.  
  
   2.  Użyj **działanie (z separacją kodu)** szablonu w celu utworzenia działanie z definicją działania, wyrażone jako znacznik przepływu pracy i kod użytkownika w osobnym pliku kodu.  
  
3. Wpisz nazwę działania lub pozostaw nazwę domyślną, a następnie kliknij **Dodaj**.  
  
   Można również utworzyć zbiór działań niestandardowych, tworząc nowy projekt typu **biblioteki działania przepływu pracy**. Aby uzyskać więcej informacji na temat tego typu projektu, zobacz [porady: Tworzenie biblioteki działań przepływu pracy (starsza wersja)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md).  
  
## <a name="configuring-an-activity"></a>Konfigurowanie działania  
 Gdy Projektant działań jest aktywna, można użyć przeglądarki właściwości do skonfigurowania właściwości wymienione w poniższej tabeli.  
  
|Właściwość|Komentarze|  
|--------------|--------------|  
|**Nazwa**|Nazwa działania.|  
|**Klasa bazowa**|Klasa bazowa, która pochodzi od klasy działania. Domyślna klasa bazowa jest [to SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020). W **właściwości** okna, kliknij przycisk **klasa bazowa** wielokropek **[...]**  do wybrania innej klasie bazowej [Wyszukaj i wybierz .NET typu, okno dialogowe (starsza wersja)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md).|  
|**Opis**|Zdefiniowane przez użytkownika opis działania.|  
|**Włączone**|Ustaw **True** domyślnie umożliwiające wykonanie działań i sprawdzania poprawności. Ustaw **False** można wyłączyć, wykonywania działań i sprawdzania poprawności. Aby uzyskać informacji na temat wykonywania działań i sprawdzania poprawności, zobacz [opracowywania działań przepływu pracy](http://go.microsoft.com/fwlink?LinkID=65024).|  
  
## <a name="adding-child-activities"></a>Dodawanie działań podrzędnych  
 Działania podrzędne można przeciągnąć z przybornika do następnego działania w przypadku projektowania. Następnie należy skonfigurować każde działanie podrzędne w przeglądarce właściwości.  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie działań przepływu pracy](http://go.microsoft.com/fwlink?LinkID=65024)   
 [Tworzenia działań niestandardowych](http://go.microsoft.com/fwlink?LinkID=65021)   
 [Działania przepływu pracy w starszej wersji](../workflow-designer/legacy-workflow-activities.md)   
 [Przykłady działań niestandardowych](http://go.microsoft.com/fwlink?LinkID=65022)   
 [Porady: Tworzenie biblioteki działań przepływu pracy (starsza wersja)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md)   
 [Używanie starszej wersji Projektanta przepływu pracy](../workflow-designer/using-the-legacy-workflow-designer.md)