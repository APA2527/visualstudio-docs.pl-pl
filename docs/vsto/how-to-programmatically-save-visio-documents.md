---
title: 'Porady: programowane zapisywanie dokumentów programu Visio'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], saving Visio documents
- Visio [Office development in Visual Studio], saving Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c3d763209d60440066df758b6c1eca087dea9b03
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906679"
---
# <a name="how-to-programmatically-save-visio-documents"></a>Porady: programowane zapisywanie dokumentów programu Visio
  Istnieje kilka sposobów na zapisywanie dokumentów programu Microsoft Office Visio:  
  
- Zapisz zmiany w istniejącym dokumencie.  
  
- Zapisz nowy dokument, lub Zapisz dokument pod nową nazwą.  
  
- Zapisz dokument z określonymi argumentami.  
  
  Aby uzyskać więcej informacji, zobacz dokumentację referencyjną VBA [Microsoft.Office.Interop.Visio.Document.Save](https://msdn.microsoft.com/library/office/ff766478.aspx) metody [Microsoft.Office.Interop.Visio.Document.SaveAs](https://msdn.microsoft.com/library/office/ff765824.aspx) metoda i [ Microsoft.Office.Interop.Visio.Document.SaveAsEx](https://msdn.microsoft.com/library/office/ff768149.aspx) metody.  
  
## <a name="save-an-existing-document"></a>Zapisz istniejący dokument  
  
### <a name="to-save-a-document"></a>Zapisywanie dokumentu  
  
-   Wywołaj `Microsoft.Office.Interop.Visio.Document.Save` metody `Microsoft.Office.Tools.Visio.Document` klasy dokumentu, który został wcześniej zapisany.  
  
     Aby wykorzystać ten przykład kodu, należy uruchomić go z `ThisAddIn` klasy w projekcie.  
  
    > [!NOTE]  
    >  `Microsoft.Office.Interop.Visio.Document.Save` Metoda zgłasza wyjątek, jeśli nowy dokument programu Visio nie został jeszcze zapisany.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#11)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#11)]  
  
## <a name="save-a-document-with-a-new-name"></a>Zapisywanie dokumentu pod nową nazwą  
 Użyj `Microsoft.Office.Interop.Visio.Document.SaveAs` metodę, aby zapisać nowy dokument lub dokument, który ma nową nazwę. Ta metoda wymaga, że podajesz nową nazwę pliku.  
  
### <a name="to-save-the-active-visio-document-with-a-new-name"></a>Aby zapisać aktywny dokument programu Visio z nową nazwą  
  
-   Wywołaj `Microsoft.Office.Interop.Visio.Document.SaveAs` metody `Microsoft.Office.Tools.Visio.Document` chcesz zapisać, korzystając z w pełni kwalifikowaną ścieżkę, łącznie z nazwą pliku. Jeśli plik o tej nazwie już istnieje w tym folderze, jest zastąpione w trybie dyskretnym.  
  
     Aby wykorzystać ten przykład kodu, należy uruchomić go z `ThisAddIn` klasy w projekcie.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#10)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#10)]  
  
## <a name="save-a-document-with-a-new-name-and-specified-arguments"></a>Zapisywanie dokumentu przy użyciu nowej nazwy i określonych argumentów  
 Użyj `Microsoft.Office.Interop.Visio.Document.SaveAsEx` metodę, aby zapisać dokument pod nową nazwą, a następnie określ wszelkie argumenty mające zastosowanie do zastosowania do dokumentu.  
  
### <a name="to-save-document-with-a-new-name-and-specified-arguments"></a>Można zapisać dokumentu z nową nazwą i określonych argumentów  
  
-   Wywołaj `Microsoft.Office.Interop.Visio.Document.SaveAsEx` metody `Microsoft.Office.Tools.Visio.Document` chcesz zapisać, korzystając z w pełni kwalifikowaną ścieżkę, łącznie z nazwą pliku. Jeśli plik o tej nazwie już istnieje w tym folderze, zwracany jest wyjątek.  
  
     Poniższy przykład kodu Zapisuje aktywny dokument pod nową nazwą, oznacza dokumentu jako tylko do odczytu i zawiera dokument na liście niedawno używane dokumenty. Aby wykorzystać ten przykład kodu, należy uruchomić go z `ThisAddIn` klasy w projekcie.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#12)]  
  
## <a name="compile-the-code"></a>Skompilować kod  
 Ten przykład kodu wymaga następujących elementów:  
  
-   Zapisz dokument, który ma nową nazwę, katalog o nazwie `Test` musi znajdować się w *Moje dokumenty* folder (Windows XP i starszych) lub *dokumenty* folder (Windows Vista).  
  
## <a name="see-also"></a>Zobacz także  
 [Rozwiązania programu Visio](../vsto/visio-solutions.md)   
 [Model obiektu Visio ― omówienie](../vsto/visio-object-model-overview.md)   
 [Porady: programowane tworzenie nowych dokumentów programu Visio](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Porady: programowane otwieranie dokumentów programu Visio](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Porady: programowane zamykanie dokumentów programu Visio](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Porady: programowane drukowanie dokumentów programu Visio](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  