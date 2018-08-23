---
title: Okno dialogowe schematy XML | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0271fa26-2205-49bd-96e0-ae1441571808
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d388dc928b2f15c084034831a4b05f9d6420a65
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675218"
---
# <a name="xml-schemas-dialog-box"></a>Schematy XML, okno dialogowe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [okno dialogowe schematy XML](https://docs.microsoft.com/visualstudio/xml-tools/xml-schemas-dialog-box).  
  
  
**Schematów XML** okno dialogowe służy do wybierania które schematy XML schematu definicji języka (XSD) do skojarzenia z dokumentu XML. Wybierz schemat z pamięci podręcznej schematów lub określ schemat, który nie znajduje się w pamięci podręcznej. Wybrane schematy są traktowane jako część zestawu schematu. Zestaw schematu jest używany dla funkcji IntelliSense, a także Walidacja dokumentów XML.  
  
 Możesz uzyskać dostęp **schematów XML** okno dialogowe, albo klikając **schematów** przycisku w oknie dialogowym właściwości dokumentu lub wybierając **schematów** z **XML** menu.  
  
## <a name="uielement-list"></a>Lista elementów UI  
 **Użyj**  
 Wybierz, jak ma być używany schemat XML.  
  
-   **Automatyczne**. W tym schemacie nie jest używany przez bieżącego dokumentu, ale są dostępne na automatyczne kojarzenie. Jeśli dokument XML deklaruje przestrzeni nazw, który odpowiada `targetNamespace` tego schematu schemat zostaną automatycznie skojarzone i znajduje się w zestawie schematów.  
  
-   **Użyj tego schematu**. Ten schemat jest on używany przez bieżącego dokumentu. Użytkownik ma jawnie zażądano, można użyć tego schematu, klikając tę kolumnę lub schemat został automatycznie skojarzone w oparciu o dopasowanie `targetNamespace`.  
  
-   **Nie używaj wybranych schematów**. W tym schemacie nie jest używany przez bieżącego dokumentu, nawet wtedy, gdy schemat miała zgodną `targetNamespace`. To ustawienie może być przydatne w przypadku rozwiązywania konfliktów, jeśli istnieje więcej niż jedna wersja ten sam schemat w pamięci podręcznej schematów lub rozwiązania.  
  
 **TARGET Namespace**  
 Wyświetla docelowego obszaru nazw, skojarzone ze schematem XML.  
  
 **Nazwa pliku**  
 Wyświetla nazwę pliku schematu XML.  
  
 **Dodaj**  
 Otwiera **otwieranie schematu XSD** okno dialogowe, które umożliwia wybranie dodatkowe schematy do dodania do zestawu schematów. Po dodaniu schematu do schematu ustawiony **użyj** jest równa wartości w kolumnie **używają tego schematu**.  
  
 **Usuń**  
 Usuwa aktualnie wybranego schematu z zestawu schematów. Spowoduje to usunięcie schematu z pamięci podręcznej schematów w pamięci, ale nie z systemu plików.  
  
## <a name="see-also"></a>Zobacz też  
 [Składniki edytora XML](../xml-tools/xml-editor-components.md)   
 [Porady: Wybieranie schematów XML do użycia](../xml-tools/how-to-select-the-xml-schemas-to-use.md)   
 [Pamięć podręczna schematów](../xml-tools/schema-cache.md)



