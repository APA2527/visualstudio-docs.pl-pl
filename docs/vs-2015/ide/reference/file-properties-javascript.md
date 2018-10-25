---
title: Plik właściwości, JavaScript | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- javascript.project.property.expandedsdknode.fileversion
- javascript.project.property.expandedsdknode.uri
- javascript.project.property.expandedsdknode.filename
- javascript.project.property.reference.description
- javascript.project.property.reference.specificversion
- javascript.project.property.reference.identity
- javascript.project.property.fullpath
- javascript.project.property.packageaction
- javascript.project.property.reference.package
- javascript.project.property.copytooutputdirectory
- javascript.project.property.expandedsdknode.sdkpath
- javascript.project.property.reference.filetype
- javascript.project.property.reference.culture
- javascript.project.property.filename
- javascript.project.property.reference.resolvedpath
- javascript.project.property.reference.version
ms.assetid: 085913b8-a97b-45f7-85fa-bbb0902f3ee9
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8db05d62bd1a8b1e1bf5fee6642810c654265c97
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49909736"
---
# <a name="file-properties-javascript"></a>Właściwości pliku, JavaScript
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Aby wskazać, jakie akcje, system projektu należy wykonać na plikach, można użyć właściwości pliku. Na przykład można ustawić właściwości pliku, aby wskazać, czy plik należy dodać do pakietu jako plik zasobów.  
  
 Można wybrać dowolny plik w Eksploratorze rozwiązań i następnie sprawdź jego właściwości w oknie dialogowym właściwości. Pliki JavaScript ma cztery właściwości: **Kopiuj do katalogu wyjściowego**, **Akcja pakietu**, **nazwy pliku**, i **ścieżka pliku**.  
  
## <a name="file-properties"></a>Właściwości pliku  
 W tej sekcji opisano właściwości wspólne dla plików JavaScript.  
  
### <a name="copy-to-output-directory-property"></a>Skopiuj do właściwości katalogu danych wyjściowych  
 Ta właściwość określa warunki, w których wybranym pliku źródłowym zostaną skopiowane do katalogu wyjściowego. Wybierz **nie Kopiuj** Jeśli plik nigdy nie ma zostać skopiowany do katalogu wyjściowego. Wybierz **zawsze Kopiuj** Jeśli plik jest zawsze był kopiowany do katalogu wyjściowego. Wybierz **Kopiuj Jeśli nowszy** Jeśli plik jest kopiowany, tylko wtedy, gdy jest nowsza niż istniejący plik o takiej samej nazwie w katalogu wyjściowym.  
  
### <a name="package-action"></a>Akcja pakietu  
 **Akcja pakietu** właściwość wskazuje co program Visual Studio przy użyciu pliku po wykonaniu kompilacji. **Pakiet akcji** może mieć jeden z kilku wartości:  
  
- **Brak** — plik nie jest uwzględniony w manifeście pakietu. Przykładem jest plik tekstowy, który zawiera dokumentację, takich jak plik Readme.  
  
- **Zawartość** — plik jest uwzględniony w manifeście pakietu. Na przykład to ustawienie jest wartością domyślną dla .htm, js, CSS, obrazów, plików audio i wideo.  
  
- **Manifest** — plik nie jest uwzględniony w manifeście pakietu. Zamiast tego pliku jest używany dla danych wejściowych podczas generowania manifestu pakietu. Jest to wartość domyślna dla pliku package.appxmanifest.  
  
- **Zasób** — plik nie jest uwzględniony w manifeście pakietu. Zamiast tego należy zawartość pliku są indeksowane w indeksie zasobów pakietu (PRI), prowadzące do manifestu pakietu. Zazwyczaj służy do plików zasobów.  
  
  Wartością domyślną dla **Akcja pakietu** zależy od rozszerzenia pliku, który można dodać do rozwiązania.  
  
### <a name="file-name-property"></a>Właściwość Nazwa pliku  
 Wyświetla nazwę pliku jako wartość tylko do odczytu. Aby zmienić nazwę pliku, należy kliknąć prawym przyciskiem myszy w Eksploratorze rozwiązań i wybrać **Zmień nazwę**.  
  
### <a name="full-path-property"></a>Pełna ścieżka właściwości  
 Wyświetla pełną ścieżkę do pliku jako wartość tylko do odczytu. Aby zmienić ścieżkę pliku, możesz przeciąganie i upuszczanie plików w Eksploratorze rozwiązań.  
  
## <a name="reference-file-properties"></a>Właściwości odwołania do pliku  
 W tej sekcji opisano typowe w plikach stanowiący odwołanie z właściwości [!INCLUDE[win8_app_js](../../includes/win8-app-js-md.md)]. Po wybraniu odwołania, takich jak plik winmd, odwołanie do zestawu SDK, odwołanie projektu do projektu lub odwołanie do zestawu w Eksploratorze rozwiązań, inne właściwości mogą być wyświetlane w oknie dialogowym właściwości zgodnie z typem pliku.  
  
### <a name="culture"></a>Kultury  
 Wyświetla język skojarzonej z odwołaniem.  
  
### <a name="file-type"></a>Typ pliku  
 Wyświetla typ pliku odwołania.  
  
### <a name="file-version"></a>Wersja pliku  
 Wyświetla wersję pliku odwołania.  
  
### <a name="identity"></a>Tożsamość  
 Wyświetla tożsamość odwołania, który jest używany w projekcie, który jest przechowywany w pliku projektu.  
  
### <a name="package"></a>Package  
 Wyświetla nazwę skojarzonej z odwołaniem manifestu pakietu.  
  
### <a name="resolved-path"></a>Rozpoznana ścieżka  
 Wyświetla ścieżkę do odwołania, który jest używany w projekcie.  
  
### <a name="sdk-path"></a>Ścieżka zestawu SDK  
 Wyświetla ścieżkę do pliku zestawu SDK.  
  
### <a name="uri"></a>Identyfikator URI  
 Wyświetla identyfikator URI, który muszą być zawarte w plikach HTML i JavaScript projektu Aby dołączyć plik jako plik źródłowy.  
  
### <a name="version"></a>Wersja  
 Wyświetla wersję odwołania.  
  
## <a name="see-also"></a>Zobacz też  
 [NIB: Właściwości projektu (Visual Studio)](http://msdn.microsoft.com/en-us/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)



