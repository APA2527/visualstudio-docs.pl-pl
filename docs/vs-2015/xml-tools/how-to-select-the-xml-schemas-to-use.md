---
title: 'Porady: Wybieranie schematów XML do użycia | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93f573412524619292b1966e87abeda11cc0813a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49863727"
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>Porady: Wybieranie schematów XML do użycia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Edytor XML udostępnia pamięci podręcznej schematów znajduje się w katalogu %InstallDir%\Xml\Schemas. Pamięci podręcznej schematów obejmuje dobrze znanych schematów XML, które są używane do weryfikacji dokumentu IntelliSense i XML.  
  
 **Schematów** właściwości dokumentu jest używany do wybierania jednego lub więcej XML schematu definicji języka (XSD) schematy do użycia. Umożliwia wybieranie schematów z pamięci podręcznej schematu lub określ schemat, który nie znajduje się w pamięci podręcznej.  
  
 Schematów, które określisz są zapisywane w ukrytym plik opcji użytkownika rozwiązania (suo) oraz wszystkie inne właściwości dokumentu XML. W rezultacie nie trzeba ponownie wprowadzić te wartości przy następnym otwarciu rozwiązania.  
  
> [!NOTE]
>  Edytora można sprawdzić poprawność przy użyciu wbudowanego schematu lub schemat przywoływany przez `xsd:schemaLocation` atrybutu. Aby uzyskać więcej informacji, zobacz [Walidacja dokumentów XML](../xml-tools/xml-document-validation.md).  
  
### <a name="to-select-an-xml-schema-from-the-schema-cache"></a>Aby wybrać schematu XML z pamięci podręcznej schematów  
  
1. Otwórz plik w edytorze XML.  
  
2. W oknie dialogowym właściwości dokumentu, kliknij przycisk **schematów** pola.  
  
    **Schematów XML** zostanie wyświetlone okno dialogowe. Okno dialogowe wyświetla listę wszystkich schematów z rozszerzeniem xsd w pamięci podręcznej schematów (w tym schematy przywoływane w pliku catalog.xml), a także żadnego schematu, który znajduje się w bieżącym rozwiązaniu, Otwórz w programie Visual Studio, do którego odwołuje się `xsd:schemaLocation` atrybut lub do których odwołuje się **schematów** właściwości.  
  
3. Wybieranie schematów do użycia w celu weryfikacji, wykonując jedną z następujących czynności:  
  
   - Wybierz schemat na liście **schematów XML** okno dialogowe, kliknij przycisk **użyj** kolumny, a następnie wybierz **używają tego schematu**.  
  
     —lub—  
  
   - Wybierz wiele schematów na liście **schematów XML** okno dialogowe, kliknij prawym przyciskiem myszy i wybierz **używają tego schematu**.  
  
4. Kliknij przycisk **OK**.  
  
    Lista wybranych schematów są kopiowane z powrotem do **schematów** właściwości dokumentu.  
  
### <a name="to-add-an-xml-schema-to-the-schema-cache"></a>Aby dodać schematu XML do pamięci podręcznej schematów  
  
1.  W oknie dialogowym właściwości dokumentu, kliknij przycisk **schematów** pola.  
  
2.  Kliknij przycisk **Dodaj**.  
  
     Spowoduje to otwarcie **otwieranie schematu XSD** okna dialogowego.  
  
3.  Przeglądaj i wybierz schematy, aby dodać do pamięci podręcznej schematów.  
  
4.  Kliknij przycisk **Otwórz**.  
  
     Schematy dodane do schematu w pamięci podręcznej i jest **użyj** jest równa wartości w kolumnie **używają tego schematu**.  
  
### <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>Aby usunąć schematu XML z pamięci podręcznej schematów  
  
1.  W oknie dialogowym właściwości dokumentu, kliknij przycisk **schematów** pola.  
  
2.  Wybierz schemat, Usuń, a następnie kliknij przycisk **Usuń**.  
  
     Schemat zostanie usunięty z pamięci podręcznej schematów w pamięci, ale nie jest on usuwany z systemu plików.  
  
    > [!NOTE]
    >  Jeśli nadal masz odwołanie do schematu za pomocą `schemaLocation` atrybutu lub pasujący obiekt typu `targetNamespace` następnie **Usuń** nie będzie działać w tej sytuacji ze względu na skojarzenie automatyczne. W takim przypadku zalecane jest, oznaczeniu schematu jako **nie używaj wybranych schematów** w **użyj** kolumny.  
  
## <a name="see-also"></a>Zobacz też  
 [Pamięci podręcznej schematów](../xml-tools/schema-cache.md)   
 [Okno dialogowe schematy XML](../xml-tools/xml-schemas-dialog-box.md)   
 [Edytor XML](../xml-tools/xml-editor.md)



