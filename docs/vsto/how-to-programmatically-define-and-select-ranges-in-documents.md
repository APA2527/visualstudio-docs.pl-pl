---
title: 'Porady: programowane definiowanie i zaznaczanie zakresów w dokumentach'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], selecting sentences
- documents [Office development in Visual Studio], ranges
- sentences, selecting in documents
- ranges, selecting in documents
- ranges, defining in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8770871bfdc361e29d7ac7c2fc984477b1ec0ea1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49833138"
---
# <a name="how-to-programmatically-define-and-select-ranges-in-documents"></a>Porady: programowane definiowanie i zaznaczanie zakresów w dokumentach
  Można zdefiniować zakres w dokumencie programu Microsoft Word pakietu Office za pomocą <xref:Microsoft.Office.Interop.Word.Range> obiektu. Wybierz cały dokument na wiele sposobów, na przykład za pomocą <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metody <xref:Microsoft.Office.Interop.Word.Range> obiektu lub przy użyciu właściwość Content <xref:Microsoft.Office.Tools.Word.Document> klasy (w dostosowaniu na poziomie dokumentu) lub <xref:Microsoft.Office.Interop.Word.Document> klasy (w Dodatek narzędzi VSTO dla).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="define-a-range"></a>Definiowanie zakresu  
 Poniższy przykład pokazuje, jak utworzyć nową <xref:Microsoft.Office.Interop.Word.Range> obiekt, który zawiera pierwszy siedem znaków w aktywnym dokumencie, w tym niedrukowalne znaki. Wybiera tekstu w zakresie.  
  
### <a name="to-define-a-range-in-a-document-level-customization"></a>Aby zdefiniować zakres w dostosowaniu na poziomie dokumentu  
  
1.  Dodaj zakres w dokumencie, przekazując początkowy i końcowy znak do <xref:Microsoft.Office.Tools.Word.Document.Range%2A> metody <xref:Microsoft.Office.Tools.Word.Document> klasy. Aby wykorzystać ten przykład kodu, należy uruchomić go z `ThisDocument` klasy w projekcie.  
  
     [!code-vb[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#18)]  
  
### <a name="to-define-a-range-by-using-a-vsto-add-in"></a>Aby zdefiniować zakres przy użyciu dodatku narzędzi VSTO  
  
1.  Dodaj zakres w dokumencie, przekazując początkowy i końcowy znak do <xref:Microsoft.Office.Interop.Word._Document.Range%2A> metody <xref:Microsoft.Office.Interop.Word.Document> klasy. Poniższy przykład kodu dodaje zakres do aktywnego dokumentu. Aby wykorzystać ten przykład kodu, należy uruchomić go z `ThisAddIn` klasy w projekcie.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#18)]  
  
## <a name="select-a-range-in-a-document-level-customization"></a>Wybierz zakres w dostosowaniu na poziomie dokumentu  
 W poniższych przykładach pokazano sposób wybierania całego dokumentu przy użyciu <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metody <xref:Microsoft.Office.Interop.Word.Range> obiektu lub przy użyciu <xref:Microsoft.Office.Tools.Word.Document.Content%2A> właściwość <xref:Microsoft.Office.Tools.Word.Document> klasy.  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Aby zaznaczyć cały dokument jako zakres przy użyciu metody Select  
  
1.  Użyj <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metody <xref:Microsoft.Office.Interop.Word.Range> zawierający całego dokumentu. Aby użyć w poniższym przykładzie kodu, należy uruchomić go z `ThisDocument` klasy w projekcie.  
  
     [!code-vb[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#19)]  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>Aby zaznaczyć cały dokument jako zakres przy użyciu właściwości zawartości  
  
1. Użyj <xref:Microsoft.Office.Tools.Word.Document.Content%2A> właściwości w celu zdefiniowania zakresu, który obejmuje cały dokument.  
  
    [!code-vb[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#20)]
    [!code-csharp[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#20)]  
  
   Aby zdefiniować zakres, można użyć metody i właściwości innych obiektów.  
  
### <a name="to-select-a-sentence-in-the-active-document"></a>Aby wybrać dowolne zdanie w aktywnym dokumencie  
  
1. Ustaw zakres przy użyciu <xref:Microsoft.Office.Interop.Word.Sentences> kolekcji. Użyj indeksu zdania, który ma zostać wybrana.  
  
    [!code-vb[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#21)]
    [!code-csharp[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#21)]  
  
   Wybierz dowolne zdanie w inny sposób to do ręcznego ustawiania wartości początkowa i końcowa zakresu.  
  
### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>Aby wybrać dowolne zdanie, należy ręcznie ustawienie wartości początkowa i końcowa  
  
1.  Utwórz zmienną zakresu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#23)]  
  
2.  Sprawdź, czy istnieją co najmniej dwa zdania w dokumencie, ustaw *Start* i *zakończenia* argumenty zakresu, a następnie wybierz zakres.  
  
     [!code-vb[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#24)]  
  
## <a name="select-a-range-by-using-a-vsto-add-in"></a>Wybierz zakres przy użyciu dodatku narzędzi VSTO  
 W poniższych przykładach pokazano sposób wybierania całego dokumentu przy użyciu <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metody <xref:Microsoft.Office.Interop.Word.Range> obiektu lub przy użyciu <xref:Microsoft.Office.Interop.Word._Document.Content%2A> właściwość <xref:Microsoft.Office.Interop.Word.Document> klasy.  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Aby zaznaczyć cały dokument jako zakres przy użyciu metody Select  
  
1.  Użyj <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metody <xref:Microsoft.Office.Interop.Word.Range> zawierający całego dokumentu. Poniższy kod wybiera zawartość aktywnego dokumentu. Aby wykorzystać ten przykład kodu, należy uruchomić go z `ThisAddIn` klasy w projekcie.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#19)]  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>Aby zaznaczyć cały dokument jako zakres przy użyciu właściwości zawartości  
  
1. Użyj <xref:Microsoft.Office.Interop.Word._Document.Content%2A> właściwości w celu zdefiniowania zakresu, który obejmuje cały dokument.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#20)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#20)]  
  
   Aby zdefiniować zakres, można użyć metody i właściwości innych obiektów.  
  
### <a name="to-select-a-sentence-in-the-active-document"></a>Aby wybrać dowolne zdanie w aktywnym dokumencie  
  
1. Ustaw zakres przy użyciu <xref:Microsoft.Office.Interop.Word.Sentences> kolekcji. Użyj indeksu zdania, który ma zostać wybrana.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#21)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#21)]  
  
   Wybierz dowolne zdanie w inny sposób to do ręcznego ustawiania wartości początkowa i końcowa zakresu.  
  
### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>Aby wybrać dowolne zdanie, należy ręcznie ustawienie wartości początkowa i końcowa  
  
1.  Utwórz zmienną zakresu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#23)]  
  
2.  Sprawdź, czy istnieją co najmniej dwa zdania w dokumencie, ustaw *Start* i *zakończenia* argumenty zakresu, a następnie wybierz zakres.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#24)]  
  
## <a name="see-also"></a>Zobacz także  
 [Model obiektu Word — omówienie](../vsto/word-object-model-overview.md)   
 [Porady: programowane rozszerzanie zakresów w dokumentach](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Porady: programowane pobieranie znaków początkowych i końcowych w zakresach](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Porady: programowane rozszerzanie zakresów w dokumentach](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Porady: programowane Resetowanie zakresów w dokumentach programu Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Porady: programowane zwijanie zakresów lub zaznaczenia w dokumentach](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Porady: programowane wykluczanie znaczników akapitu podczas tworzenia zakresów](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  
  