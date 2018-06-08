---
title: 'Wskazówki: Tworzenie menu skrótów dla zakładek'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context menus, Word
- Bookmark control, events
- shortcut menus, Word
- menus, creating in Office applications
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8153f0120259eec8ad284b0717e58be750e3b99d
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845733"
---
# <a name="walkthrough-create-shortcut-menus-for-bookmarks"></a>Wskazówki: Tworzenie menu skrótów dla zakładek
  Ten przewodnik przedstawia sposób tworzenia menu skrótów <xref:Microsoft.Office.Tools.Word.Bookmark> formantów w dostosowaniu poziomie dokumentu dla programu Word. Po kliknięciu tekstu zakładki menu skrótów pojawia się i udostępnia opcje użytkownika dla formatowania tekstu.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 W instruktażu przedstawiono następujące zagadnienia:  
  
-   [Utwórz projekt](#BKMK_CreateProject).  
  
-   [Dodawanie tekstu i zakładki w dokumencie](#BKMK_addtextandbookmarks).  
  
-   [Dodawanie poleceń do menu skrótów](#BKMK_AddCmndsShortMenu).  
  
-   [Formatowanie tekstu w zakładce](#BKMK_formattextbkmk).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 Następujące składniki są wymagane do przeprowadzenia tego instruktażu:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] lub [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
##  <a name="BKMK_CreateProject"></a> Tworzenie projektu  
 Pierwszym krokiem jest utworzenie projektu dokument programu Word w programie Visual Studio.  
  
### <a name="to-create-a-new-project"></a>Aby utworzyć nowy projekt  
  
-   Tworzenie projektu dokument programu Word o nazwie **Moje Menu skrótów zakładki**. W kreatorze Wybierz **Utwórz nowy dokument**. Aby uzyskać więcej informacji, zobacz [porady: tworzenie projektach pakietu Office w Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio zostanie otwarty nowy dokument programu Word w Projektancie i dodaje **Moje Menu skrótów zakładki** projektu do **Eksploratora rozwiązań**.  
  
##  <a name="BKMK_addtextandbookmarks"></a> Dodawanie tekstu i zakładki w dokumencie  
 Dodaj część tekstu do dokumentu, a następnie dodaj dwie nakładające się zakładki.  
  
### <a name="to-add-text-to-your-document"></a>Aby dodać tekstu do dokumentu  
  
-   W dokumencie, który zostanie wyświetlony w Projektancie projektu tekst.  
  
     **Jest to przykład tworzenia menu skrótów po kliknięciu prawym przyciskiem myszy tekstu zakładki.**  
  
### <a name="to-add-a-bookmark-control-to-your-document"></a>Aby dodać kontrolkę zakładki w dokumencie  
  
1.  W **przybornika**, z **formanty Word** karcie, przeciągnij <xref:Microsoft.Office.Tools.Word.Bookmark> formantu do dokumentu.  
  
     **Dodaj formant zakładki** zostanie wyświetlone okno dialogowe.  
  
2.  Wybierz wyrazy "Tworzenie menu skrótów po kliknięciu prawym przyciskiem myszy tekst", a następnie kliknij przycisk **OK**.  
  
     `bookmark1` zostanie dodany do dokumentu.  
  
3.  Dodaj inny <xref:Microsoft.Office.Tools.Word.Bookmark> kontrolować wyrazy "kliknij prawym przyciskiem tekstu zakładki".  
  
     `bookmark2` zostanie dodany do dokumentu.  
  
    > [!NOTE]  
    >  Wyrazy "kliknij prawym przyciskiem tekst" są zarówno `bookmark1` i `bookmark2`.  
  
 Po dodaniu zakładki w dokumencie w czasie projektowania <xref:Microsoft.Office.Tools.Word.Bookmark> formant nie zostanie utworzony. Można zaprogramować przed kilka zdarzeń zakładki. Możesz pisać kod <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick> zdarzeń zakładki tak, aby po kliknięciu tekstu zakładki, zostanie wyświetlone menu skrótów.  
  
##  <a name="BKMK_AddCmndsShortMenu"></a> Dodawanie poleceń do menu skrótów  
 Dodawanie przycisków do menu skrótów, które pojawia się po kliknięciu prawym przyciskiem myszy dokument.  
  
### <a name="to-add-commands-to-a-shortcut-menu"></a>Aby dodać polecenia do menu skrótów  
  
1.  Dodaj **kodu XML wstążki** elementu do projektu. Aby uzyskać więcej informacji, zobacz [porady: wprowadzenie do dostosowywania wstążki](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
2.  W **Eksploratora rozwiązań**, wybierz pozycję **ThisDocument.cs** lub **ThisDocument.vb**.  
  
3.  Na pasku menu wybierz **widoku** > **kod**.  
  
     **ThisDocument** klasy plik zostanie otwarty w edytorze kodu.  
  
4.  Dodaj następujący kod do **ThisDocument** klasy. Ten kod zastępuje metodę CreateRibbonExtensibilityObject i zwraca klasy XML wstążki do aplikacji pakietu Office.  
  
     [!code-csharp[Trin_Word_Document_Menus#1](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#1)]
     [!code-vb[Trin_Word_Document_Menus#1](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#1)]  
  
5.  W **Eksploratora rozwiązań**, wybierz plik XML wstążki. Domyślnie plik XML wstążki nosi nazwę Ribbon1.xml.  
  
6.  Na pasku menu wybierz **widoku** > **kod**.  
  
     Plik xml wstążki, zostanie otwarty w edytorze kodu.  
  
7.  W edytorze kodu Zastąp zawartość pliku XML wstążki z następującym kodem.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8"?>  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui" onLoad="Ribbon_Load">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="BoldButton" label="Bold" onAction="ButtonClick"          
               getVisible="GetVisible" />  
          <button id="ItalicButton" label="Italic" onAction="ButtonClick"   
              getVisible="GetVisible"/>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
     Ten kod dodaje dwa przyciski do menu skrótów, które pojawia się po kliknięciu prawym przyciskiem myszy dokument.  
  
8.  W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy `ThisDocument`, a następnie kliknij przycisk **kod widoku**.  
  
9. Deklarowanie następujące zmienne i zmienną zakładki na poziomie klasy.  
  
     [!code-csharp[Trin_Word_Document_Menus#2](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#2)]
     [!code-vb[Trin_Word_Document_Menus#2](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#2)]  
  
10. W **Eksploratora rozwiązań**, wybierz plik kodu wstążki. Domyślnie, nosi nazwę pliku kodu wstążki **Ribbon1.cs** lub **Ribbon1.vb**.  
  
11. Na pasku menu wybierz **widoku** > **kod**.  
  
     Plik wstążki kodu zostanie otwarty w edytorze kodu.  
  
12. W pliku kodu wstążki Dodaj następującą metodę. Jest to metoda wywołania zwrotnego dla dwóch przycisków dodanych do menu skrótów dokumentu. Ta metoda określa, czy przyciski są wyświetlane w menu skrótów. Przyciski pogrubionego oraz pochylonego są wyświetlane tylko wtedy, gdy kliknij prawym przyciskiem myszy tekst w zakładce.  
  
     [!code-csharp[Trin_Word_Document_Menus#5](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/ribbon1.cs#5)]
     [!code-vb[Trin_Word_Document_Menus#5](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/ribbon1.vb#5)]  
  
##  <a name="BKMK_formattextbkmk"></a> Formatowanie tekstu zakładki  
  
### <a name="to-format-the-text-in-the-bookmark"></a>Formatowanie tekstu zakładki  
  
1.  W pliku kodu wstążki, Dodaj `ButtonClick` obsługi zdarzeń do formatowania do zakładki.  
  
     [!code-csharp[Trin_Word_Document_Menus#6](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/ribbon1.cs#6)]
     [!code-vb[Trin_Word_Document_Menus#6](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/ribbon1.vb#6)]  
  
2.  **Eksplorator rozwiązań**, wybierz pozycję **ThisDocument.cs** lub **ThisDocument.vb**.  
  
3.  Na pasku menu wybierz **widoku** > **kod**.  
  
     **ThisDocument** klasy plik zostanie otwarty w edytorze kodu.  
  
4.  Dodaj następujący kod do **ThisDocument** klasy.  
  
     [!code-csharp[Trin_Word_Document_Menus#3](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#3)]
     [!code-vb[Trin_Word_Document_Menus#3](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#3)]  
  
    > [!NOTE]  
    >  Należy napisać kod obsługi w przypadku nakładają się zakładki. Jeśli nie, domyślnie kod zostanie wywołana dla wszystkie zakładki w zaznaczeniu.  
  
5.  W języku C#, należy dodać obsługę zdarzeń dla formantów zakładek do <xref:Microsoft.Office.Tools.Word.Document.Startup> zdarzeń. Aby uzyskać informacje dotyczące tworzenia procedury obsługi zdarzeń, zobacz [porady: tworzenie obsługi zdarzeń w projektach pakietu Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_Word_Document_Menus#4](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#4)]  
  
## <a name="test-the-application"></a>Testowanie aplikacji  
 Przetestuj dokumencie, aby sprawdzić, czy elementy menu pogrubionego oraz pochylonego są wyświetlane w menu skrótów po kliknięciu prawym przyciskiem myszy tekstu zakładki i tekst jest poprawnie sformatowana.  
  
### <a name="to-test-your-document"></a>Aby przetestować dokumentu  
  
1.  Naciśnij klawisz **F5** do uruchomienia projektu.  
  
2.  Kliknij prawym przyciskiem myszy w pierwszym zakładki, a następnie kliknij przycisk **Bold**.  
  
3.  Upewnij się, że cały tekst w `bookmark1` jest sformatowany jako pogrubiony.  
  
4.  Kliknij prawym przyciskiem myszy tekstu zakładki nakładają się, a następnie kliknij przycisk **Kursywa**.  
  
5.  Upewnij się, że cały tekst w `bookmark2` jest kursywa i tylko część tekstu w `bookmark1` która pokrywa się `bookmark2` jest kursywą.  
  
## <a name="next-steps"></a>Następne kroki  
 Poniżej przedstawiono niektóre zadania, które mogą występować:  
  
-   Pisanie kodu w celu reagowania na zdarzenia formanty hosta w programie Excel. Aby uzyskać więcej informacji, zobacz [wskazówki: Program w odniesieniu do zdarzeń formantu NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  
  
-   Pole wyboru umożliwia zmienianie formatowania w zakładki. Aby uzyskać więcej informacji, zobacz [wskazówki: dokument Zmienianie formatowania za pomocą formantów CheckBox](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Wskazówki dotyczące przy użyciu programu Word](../vsto/walkthroughs-using-word.md)   
 [Dostosowywanie interfejsu użytkownika pakietu Office](../vsto/office-ui-customization.md)   
 [Automatyzowanie programu Word za pomocą obiektów rozszerzonych](../vsto/automating-word-by-using-extended-objects.md)   
 [BOOKMARK, formant:](../vsto/bookmark-control.md)   
 [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  