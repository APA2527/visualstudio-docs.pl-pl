---
title: Funkcje IntelliSense w edytorze XML | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b26f214-cc3a-46bf-b260-14eb8e599182
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 983410eec11799fb05ad66e13df1aea95be8e8f3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630736"
---
# <a name="xml-editor-intellisense-features"></a>Funkcje IntelliSense w edytorze XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [funkcje IntelliSense w edytorze XML](https://docs.microsoft.com/visualstudio/xml-tools/xml-editor-intellisense-features).  
  
  
Edytor XML udostępnia pełne funkcje IntelliSense porównywalne do innych edytorów języka podany w programie Visual Studio. W tej sekcji opisano, jak za pomocą funkcji IntelliSense języka definicji schematu XML (XSD) i dokumentów XSLT.  
  
## <a name="intellisense-in-an-xsd-document"></a>Funkcja IntelliSense w dokumencie XSD  
 Po schemat jest powiązany z dokumentem, masz dostęp do listy rozwijanej listy elementów oczekiwanego dowolnej chwili możesz wpisać `"<"` lub kliknij przycisk **wyświetlania listy członków obiektu** na listwie narzędziowej edytora XML. Aby uzyskać informacje o sposobach kojarzenia schematów z dokumentami XML, zobacz [Walidacja dokumentów XML](../xml-tools/xml-document-validation.md).  
  
 Podczas wpisywania tekstu ilość miejsca od wewnątrz tagu początkowego, możesz także uzyskać listy rozwijanej, przedstawiający wszystkie atrybuty, które mogą być dodawane do bieżącego elementu.  
  
 Podczas wpisywania `"="` dla wartości atrybutu lub cudzysłów otwierający dla wartości, możesz również uzyskać listę możliwych wartości dla tego atrybutu. Wartości są podane tylko, jeśli schemat zawiera wyliczany wartości zwrotne za pośrednictwem `xsd:enumeration` aspektami, czy dany atrybut znajduje się `Boolean` typu. Lista IntelliSense kodów znanych języków znajduje się również do `xml:lang` lub dowolnego `simpleType` który pochodzi od klasy `xsd:language`. Funkcja IntelliSense listę znanych `targetNamespace` wartości towarzyszy deklaracje przestrzeni nazw.  
  
 Technologia IntelliSense listę możliwych wartości jest również udostępniany, gdy wpiszesz `">"` zamknięcie tagu początkowego, jeśli element jest `simpleType`. Zachowanie elementów jest podobne do zachowania w przypadku atrybutów, które opisano w poprzednim akapicie.  
  
 Etykietki narzędzi są również wyświetlane na listach tych technologii IntelliSense, na podstawie `xsd:annotation` i `xsd:documentation` informacje znaleźć skojarzonego schematu.  
  
## <a name="intellisense-in-an-xslt-document"></a>Funkcja IntelliSense w dokumencie XSLT  
 Po dodaniu szablonie o podanej nazwie lub atrybutu w dokumencie XSLT, można użyć funkcji IntelliSense do wstawienia następujące czynności:  
  
-   Ustawić atrybutu nazwy.  
  
-   Tryby szablonu.  
  
-   Nazwy szablonu.  
  
-   Nazwy parametrów w danym trybie.  
  
-   Nazwy parametru dla danego szablonie o podanej nazwie.  
  
 Aby uzyskać więcej informacji, zobacz [Instruktaż: za pomocą XSLT IntelliSense](../xml-tools/walkthrough-using-xslt-intellisense.md) tematu.  
  
## <a name="auto-completion"></a>Automatyczne uzupełnianie  
 Edytor XML sprawia, że łatwiej XML do edycji, wypełniając wymaganej składni XML dla Ciebie. Jeśli na przykład wpisz następujący tag początkowy:  
  
 `<book>`  
  
 Edytor XML wypełnia tagu końcowego i umieszcza kursor po tagu początkowego. Oto przykład ("&#124;" Uwagi dotyczące pozycja kursora):  
  
 `<book>`&#124;`</book>`  
  
 Ponieważ wartości atrybutów musi zawsze mieć cudzysłowów, to edytor XML wypełnia cudzysłowów. Na przykład, wpisz następujące polecenie:  
  
 `<book title=`  
  
 Edytor XML dodaje cudzysłowu i umieszcza kursor w cudzysłowie:  
  
 `<book title="`&#124;`"`  
  
 Podobnie w edytorze XML również wstawia następującą składnię XML automatycznie dla Ciebie:  
  
-   Zakończenie instrukcji przetwarzania:  `?>`  
  
-   Koniec bloku CDATA: `]]>`  
  
-   Zakończenie komentarz: `-->`  
  
-   Zakończenie deklaracja DTD: `>`  
  
 Edytor XML ma również możliwość wstawiania przestrzeń nazw deklaracji, jeśli zostanie wybrany element kwalifikowaną przestrzeń nazw lub atrybutu z listy technologii IntelliSense i przestrzeń nazw dla tego elementu lub atrybutu nie jest jeszcze w zakresie.  
  
 Na przykład w przypadku wybrania `e:Book` elementu z listy technologii IntelliSense, w którym powiązany jest prefiks `http://books` przestrzeni nazw, która nie została zadeklarowana w dokumencie, w edytorze XML wstawia deklaracja wymaganej przestrzeni nazw. Wynikowy tekstu XML jest następująca:  
  
 `<e:Book xmlns:e="http://books"`  
  
## <a name="brace-matching"></a>Parowanie nawiasów klamrowych  
 Edytor XML zawiera nawias klamrowy wyróżnianie umożliwiają natychmiastowe informacje zwrotne na elementy, które zostały zamknięte. Można również Użyj skrótu klawiaturowego (CTRL +]), aby przejść z jednego nawias klamrowy do pasującego nawiasu klamrowego.  
  
 Edytor XML ma następujące efekty dla następujących elementów:  
  
-   Dopasowywanie tagiem początkowym i końcowym.  
  
-   Jakaś para "\<" lub ">" nawiasy.  
  
-   Początek i koniec komentarzy.  
  
-   Początek i koniec instrukcji przetwarzania.  
  
-   Początek i koniec bloki CDATA.  
  
-   Początek i koniec DTD deklaracji.  
  
-   Otwieranie i zamykanie cudzysłowy atrybutów.  
  
## <a name="modifying-the-intellisense-options"></a>Modyfikowanie opcji IntelliSense  
 Funkcje IntelliSense i automatycznego uzupełniania są domyślnie włączone. Jednak możesz to zmienić, modyfikując ustawienia opcji narzędzi.  
  
 **Automatyczne wstawianie** części **różne** kontrolki strony następujące zachowanie:  
  
|Nazwa|Opis|  
|----------|-----------------|  
|Zamknij tagów|Wstawia Zamknij tagów dla nowych elementów.|  
|Cudzysłowy atrybutu|Wstawia cudzysłowy wartości atrybutów, gdy wprowadzasz nazwę nowego atrybutu.|  
|Innych znaczników|Kończy komentarze, CDATA, elementu DOCTYPE, instrukcje przetwarzania i innych deklaracji znaczników.|  
  
#### <a name="to-change-the-auto-completion-behavior"></a>Aby zmienić zachowanie automatyczne uzupełnianie  
  
1.  Wybierz **opcje** z **narzędzia** menu.  
  
2.  Rozwiń **edytora tekstów**, rozwiń węzeł **XML**i wybierz **różne**.  
  
3.  Wprowadzaj żadnych zmian w **automatyczne wstawianie** sekcji, a następnie kliknij przycisk **OK**.  
  
## <a name="see-also"></a>Zobacz też  
 [Edytor XML](../xml-tools/xml-editor.md)   
 [Za pomocą funkcji IntelliSense](../ide/using-intellisense.md)   
 [Przewodnik: Używanie XSLT IntelliSense](../xml-tools/walkthrough-using-xslt-intellisense.md)



