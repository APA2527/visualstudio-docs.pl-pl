---
title: Wybieranie szablonu rozwiązania dotyczącego języka specyficznego dla domeny | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language Tools, solution templates
ms.assetid: 9c05955f-1548-4df6-b09b-4b348823c237
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: cded93126f4e02aa5f0417819c7a76f17e0da6d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692321"
---
# <a name="choosing-a-domain-specific-language-solution-template"></a>Wybieranie szablonu rozwiązania dotyczącego języka specyficznego dla domeny
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Wybieranie szablonu rozwiązania dotyczącego języka specyficznego dla domeny](https://docs.microsoft.com/visualstudio/modeling/choosing-a-domain-specific-language-solution-template).  
  
Aby utworzyć rozwiązanie języka dotyczącego określonej domeny, wybierz jedną z szablonów rozwiązań, które są dostępne w Kreatorze projektanta języka specyficznego dla domeny. Wybierając szablon, który najbardziej przypomina język, który ma zostać utworzona, można zminimalizować modyfikacjach, które należy podjąć, począwszy od rozwiązania.  
  
 Następujące szablony rozwiązań są dostępne w Kreatorze projektanta języka specyficznego dla domeny.  
  
> [!NOTE]
>  Celem szablonów jest zapewnienie początkowy DSL. Szablony o nazwie diagramów klas i składników nie są pełne diagramów UML. Jeśli chcesz utworzyć UML model, należy wziąć pod uwagę modelowania narzędzia, które zapewniają zestaw diagramy, które są zintegrowane w jednym modelu UML. Są rozszerzalne i może zostać zintegrowany z DSL za pomocą ModelBus. Aby uzyskać więcej informacji, zobacz [tworzenie modeli aplikacji](../modeling/create-models-for-your-app.md).  
  
|Szablon|Funkcje|Opis|  
|--------------|--------------|-----------------|  
|Diagramy klas|-Kształtów przedziałów<br />— Dziedziczenie klasa<br />-Relacji dziedziczenia<br />-Kształt dziedziczenia<br />— Właściwości relacji|Użyj tego szablonu rozwiązania, jeśli zawiera języka specyficznego dla domeny, jednostki i relacje, które mają właściwości. Ten szablon umożliwia utworzenie języka specyficznego dla domeny, podobny diagramów klas UML. Obiekty główne są klasy i interfejsy, wraz z relacji skojarzenia, generalizacji i wdrażanie. Klasy lub interfejsu jest wyświetlany jako okno, który zawiera listę atrybutów.|  
|Diagramy składników|— Porty|Użyj tego szablonu rozwiązania, jeśli języka specyficznego dla domeny obejmuje składniki, czyli części systemu oprogramowania. Ten szablon umożliwia utworzenie języka specyficznego dla domeny, który przypomina diagramy składników UML. Obiekty główne są składniki i portów, które są wyświetlane jako małe kształty na zewnątrz składników.|  
|Diagramy przepływu zadań|— Obrazów i kształtów geometrycznych<br />-   *Swimlanes*|Użyj tego szablonu rozwiązania, jeśli języka specyficznego dla domeny zawiera przepływy pracy, Państwa lub sekwencji. Ten szablon umożliwia utworzenie języka specyficznego dla domeny, który przypomina diagramy aktywności UML. Jednostki głównej jest działaniem, a relacji głównego jest przejście między działaniami. Szablon zawiera kilka innych elementów, takich jak stan początkowy stan końcowy i pasek synchronizacji.|  
|Minimalny języka|-Jedną klasę i kształt<br />-Jednej relacji i łącznik|Użyj tego szablonu rozwiązania, jeśli języka specyficznego dla domeny wygląda inaczej niż inne szablony. Ten szablon umożliwia utworzenie języka specyficznego dla domeny, który ma dwie klasy i jedna relacja, które są reprezentowane w **przybornika** jako **pole** i **wiersza**. Klasa, jak i relacji ma przykład właściwość ciągu.|  
|Minimalny projektanta formularza systemu Windows|-Małe model.<br />-Windows formularz, który wyświetla model.|Użyj tego szablonu, aby skompilować aplikację, w którym DSL jest powiązany z formularzem Windows, a nie graficznego projektanta.<br /><br /> Formularz, który działa jako interfejs użytkownika dla języka znajduje się w folderze Dsl\UI.<br /><br /> Należy skompilować projekt przed otwarciem projektanta formularzy.<br /><br /> Aby uzyskać więcej informacji, zobacz [Tworzenie języka specyficznego dla domeny Windows Forms-Based](../modeling/creating-a-windows-forms-based-domain-specific-language.md).|  
|Projektant WPF minimalny|-Małe modelu<br />— Windows Presentation Foundation interfejs użytkownika, który wyświetla model|Użyj tego szablonu, aby skompilować aplikację, w którym DSL jest powiązany z interfejsem użytkownika WPF, a nie graficznego projektanta.<br /><br /> Projektant interfejsu użytkownika znajduje się w folderze Dsl\UI.<br /><br /> Należy skompilować projekt przed otwarciem projektanta interfejsu użytkownika.<br /><br /> Aby uzyskać więcej informacji, zobacz [Tworzenie języka specyficznego dla domeny WPF-Based](../modeling/creating-a-wpf-based-domain-specific-language.md).|  
|Biblioteka DSL|— Biblioteka minimalny|Użyj tego szablonu, jeśli chcesz skompilować częściową definicję DSL, który można zaimportować do innych definicji DSL.|  
  
## <a name="see-also"></a>Zobacz też  
 [Przegląd narzędzi języka specyficznego dla domeny](../modeling/overview-of-domain-specific-language-tools.md)



