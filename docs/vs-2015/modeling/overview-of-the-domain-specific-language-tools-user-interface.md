---
title: Omówienie języka specyficznego dla domeny narzędzi interfejsu użytkownika | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
ms.assetid: 81ae6b35-6819-41d0-953b-6b4ed81f9227
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 2d88c7ee14acc1916e56010784224f8e44b73f45
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49251436"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Omówienie interfejsu użytkownika narzędzi językowych właściwych dla domeny
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Po pierwszym otwarciu rozwiązania narzędzia języka specyficznego dla domeny (narzędzia DSL), w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], interfejs użytkownika będzie przypominał na poniższej ilustracji.  
  
 ![Projektant DSL](../modeling/media/dsl-designer.png "dsl_designer")  
  
 W poniższej tabeli opisano, jak są używane elementy interfejsu użytkownika.  
  
|**Element**|**Definicja**|  
|-----------------|--------------------|  
|Diagram|Model domeny są wyświetlane na diagramie.<br /><br /> Diagram ma dwie strony. Z jednej strony definiuje typy elementów w ramach modeli. Druga strona definiuje wygląd swoje modele na ekranie.|  
|Przybornik|Przeciągnij narzędzia z przybornika, aby dodać klasy domeny i kształtów typów do diagramu. Aby dodać relacje, łączników i mapowania kształtów, kliknij narzędzie, a następnie kliknij węzeł źródła na diagramie, a następnie węzeł docelowy.|  
|Eksplorator modelu DSL|**Eksplorator modelu DSL** jest wyświetlany, gdy w definicji DSL jest aktywnym oknem. Język DSL jest wyświetlany jako drzewa. Eksplorator modelu DSL pozwala edytować funkcje modelu, które nie są wyświetlane na diagramie. Na przykład Dodaj elementy przybornika i przełączać w trakcie procesu walidacji za pomocą **Eksplorator DSL**.|  
|Okno Szczegóły języka DSL|**Szczegóły języka DSL** okno pokazuje właściwości domeny elementy modelu, które pozwalają kontrolować sposób wyświetlania elementów i jak elementy są kopiowane i usunąć.<br /><br /> -Domyślnie **szczegóły języka DSL** okno jest wyświetlane obok pola **lista błędów** i **dane wyjściowe** systemu windows.|  
  
## <a name="the-domain-model-diagram"></a>Diagram modelu domeny  
 Diagram modelu domeny jest podzielona na dwie części. Po jednej stronie diagramu zawiera określone elementy i relacje w modelu. Druga strona pokazuje, jak model, który jest wyświetlany i zawiera kształty, które są używane do wyświetlania elementów i właściwości diagramu modelu. Na poniższej ilustracji przedstawiono elementy diagramu.  
  
 ![Projektant DSL za pomocą toru](../modeling/media/dsl-desinger.png "dsl_desinger")  
  
 W poniższej tabeli opisano niektóre elementy diagramu modelu domeny.  
  
|**Termin**|**Definicja**|  
|--------------|--------------------|  
|Klasa domeny|Klasy domeny są typy elementów w ramach modeli.<br /><br /> Klasy domeny może występować więcej niż jeden raz na diagramie, jeśli jest to element docelowy więcej niż jedną relację.<br /><br /> Aby dodać klasę domeny, przeciągnij narzędzie klasę domeny z **przybornika** do **klasy i relacje** stronie diagramu.|  
|Relacja domeny|Relacje domeny są typy łączy między elementami w ramach modeli.<br /><br /> *Relacja osadzania* wskazuje, czy element docelowy jest właścicielem lub zawartej w elemencie źródłowym i jest wyświetlany jako linię ciągłą. Każdy element w modelu należy celem jedna relacja osadzania, tak, czy model formularzy drzewa. A *odwoływać się do relacji* oznacza ogólne łącza między elementami modelu i jest wyświetlana jako linia przerywana. Każdy element może mieć dowolną liczbę łączy odnośnika.<br /><br /> Utwórz relację, klikając narzędzie **przybornika**, klikając klasy domeny źródłowej, a następnie klikając klasy docelowej.|  
|Kształty i łączniki|Kształty, określ, jak elementy modelu powinien być wyświetlany na diagram DSL., łączników określić wiersze na diagramie DSL, który może służyć do wyświetlania relacji.<br /><br /> Aby utworzyć łącznik lub kształt, przeciągnij narzędzie do **elementów diagramu** stronie diagramu.|  
|Mapowania kształtów|Mapowanie kształtów pojawia się jako linia na diagram modelu domeny, konsolidacji kształt do klasy domeny, który jest wyświetlany, lub łącznik do relacji domeny, który jest wyświetlany.|  
  
## <a name="see-also"></a>Zobacz też  
 [Przegląd narzędzi języka specyficznego dla domeny](../modeling/overview-of-domain-specific-language-tools.md)   
 [Słownik narzędzi języka specyficznego dla domeny](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [Dostosowywanie i rozszerzanie języka specyficznego dla domeny](../modeling/customizing-and-extending-a-domain-specific-language.md)



