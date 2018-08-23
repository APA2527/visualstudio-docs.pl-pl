---
title: 'Porady: tworzenie fragmentów kodu XML | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8556dd7-1382-4af7-ba80-3e873c9416be
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5ed45a3cf0be913158ffa3cd82c243fc37aca8ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691703"
---
# <a name="how-to-create-xml-snippets"></a>Porady: tworzenie fragmentów kodu XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: tworzenie fragmentów kodu XML](https://docs.microsoft.com/visualstudio/xml-tools/how-to-create-xml-snippets).  
  
  
Edytor XML może służyć do tworzenia nowych fragmentów kodu XML. Edytor zawiera fragment XML o nazwie "Fragment", oznacza to fragment standardowy do tworzenia nowych fragmentów kodu XML.  
  
## <a name="to-create-a-new-xml-snippet"></a>Aby utworzyć nowy fragment kodu XML  
 Aby utworzyć nowy kod XML fragment kodu tworzy nowy plik XML i użyj **Wstaw fragment kodu** funkcji.  
  
1.  Na **pliku** menu, kliknij przycisk **New** a następnie kliknij przycisk **pliku**.  
  
2.  Kliknij przycisk **pliku XML** a następnie kliknij przycisk **Otwórz**.  
  
3.  Kliknij prawym przyciskiem myszy w okienku edytora, a następnie wybierz pozycję **Wstaw fragment kodu**.  
  
4.  Wybierz **fragment** z listy i naciśnij klawisz ENTER.  
  
5.  Wprowadź wszelkie zmiany do nowego fragmentu kodu.  
  
6.  Z **pliku** menu wybierz opcję **Zapisz XMLFile.xml**.  
  
     **Zapisz plik jako** zostanie wyświetlone okno dialogowe.  
  
7.  Wprowadź nazwę dla nowego fragmentu kodu, a następnie wybierz pozycję **pliki fragmentu kodu** z **Zapisz jako typ** okna listy rozwijanej.  
  
8.  Użyj **Zapisz w** listy rozwijanej, aby zmienić lokalizację pliku do folderu fragmentów kodu XML Snippets\XML\My 2005\Code My Documents\Visual Studio, a następnie naciśnij klawisz **Zapisz**.  
  
## <a name="snippet-description"></a>Opis fragmentu kodu  
 W tej sekcji opisano niektóre kluczowe elementy we fragmencie standardowy. Aby uzyskać więcej informacji na temat elementów schematu posługują się fragmentów kodu XML, zobacz [dokumentacja schematu fragmentów kodu](../ide/code-snippets-schema-reference.md).  
  
### <a name="snippettype-element"></a>Element SnippetType  
 Edytor obsługuje dwa typy fragmentu kodu:  
  
```  
<SnippetTypes>  
  <SnippetType>SurroundsWith</SnippetType>  
  <SnippetType>Expansion</SnippetType>  
</SnippetTypes>  
```  
  
 `Expansion` Typ Określa, czy ten fragment kodu jest wyświetlany, gdy wywołujesz **Wstaw fragment kodu** polecenia. `SurroundsWith` Typ Określa, czy ten fragment kodu jest wyświetlany, gdy wywołujesz **otacza przy użyciu** polecenia.  
  
### <a name="code-element"></a>Element Code  
 `Code` Element definiuje tekstu XML, który zostanie wstawiony podczas wywoływania fragmencie kodu.  
  
> [!NOTE]
>  Tekst fragment kodu XML muszą być ujęte w `<![CDATA[...]]>` sekcji.  
  
 Poniżej przedstawiono `Code` element, który jest tworzony przez fragment kodu standardowy.  
  
```  
<Code Language="XML">  
  <![CDATA[<test>  
  <name>$name$</name>  
  $selected$ $end$</test>]]>  
</Code>  
```  
  
 `Code` Element zawiera trzy zmienne.  
  
-   $name$ jest zmienną zdefiniowaną przez użytkownika. Tworzy `name` element, który ma wartość można edytować wartość domyślna to "name". Zmienne zdefiniowane przez użytkownika są definiowane przy użyciu `Literal` elementu.  
  
-   $ $wybrane to uprzednio zdefiniowanej zmiennej. Reprezentuje tekst, który został wybrany w edytorze XML przed wywołaniem do fragmentu kodu. Położenie ta zmienna Określa, gdzie zaznaczony tekst pojawia się we fragmencie kodu, który otacza wybieranie.  
  
-   $end$ jest uprzednio zdefiniowanej zmiennej. Gdy użytkownik naciśnie ENTER, aby zakończyć edytowanie pola fragment kodu, ta zmienna Określa, gdzie daszek (^) jest przenoszony do.  
  
 Powyższe `Code` wstawia element następujący tekst XML:  
  
```  
<test>  
  <name>name</name>  
</test>  
```  
  
 Wartość elementu name jest oznaczona jako regionem edytowalnym.  
  
### <a name="literal-element"></a>Element Literal  
 `Literal` Element jest używany do identyfikowania tekst zastępczy, który można dostosować po wstawieniu do pliku. Na przykład ciągi literałowe, wartości liczbowe i nazwy niektórych zmiennych może być zadeklarowana jako literały. Można zdefiniować dowolną liczbę literałów w fragmentu kodu XML i mogą odwoływać się do nich wiele razy w tym fragmencie kodu. Oto przykład `Literal` element, który definiuje zmienną $ $name, której domyślna wartość to "name".  
  
```  
<Literal>  
  <ID>name</ID>  
  <Default>name</Default>  
</Literal  
```  
  
 Literały znajdują się funkcje. Edytor XML zawiera funkcję o nazwie **LookupPrefix**. **LookupPrefix** funkcja wyszukuje dany identyfikator URI przestrzeni nazw z lokalizacji w dokumencie XML, w tym fragmencie kodu jest wywoływany z i zwraca prefiks przestrzeni nazw zdefiniowanej dla tego obszaru nazw, jeśli istnieje i zawiera dwukropek (:) w tej nazwie. Oto przykład `Literal` element, który używa **LookupPrefix** funkcji.  
  
```  
<Literal Editable="false">  
   <ID>prefix</ID>  
   <Function>LookupPrefix("namespaceURI")</Function>  
</Literal>  
```  
  
 Zmienna $ $prefix mogą używane gdzie indziej w fragmentu kodu XML.  
  
## <a name="see-also"></a>Zobacz też  
 [Fragmentów kodu XML](../xml-tools/xml-snippets.md)   
 [Porady: używanie fragmentów kodu XML](../xml-tools/how-to-use-xml-snippets.md)   
 [Instrukcje: Generowanie fragmentu kodu XML na podstawie schematu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)



