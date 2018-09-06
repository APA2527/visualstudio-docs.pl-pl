---
title: 'Porady: Odczyt z i zapisu do właściwości dokumentu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
- Excel [Office development in Visual Studio], document properties
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 14cecb63e7f96e58b17672bbb5cb67a345b9ece8
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677598"
---
# <a name="how-to-read-from-and-write-to-document-properties"></a>Porady: Odczyt z i zapisu do właściwości dokumentu
  Można zapisać właściwości dokumentu z dokumentu. Aplikacje pakietu Office zapewniają szereg wbudowanych właściwości, takie jak tworzenie, tytuł i temat. W tym temacie przedstawiono sposób ustawiania właściwości dokumentu w programie Microsoft Office Excel i Microsoft Office Word.  
  
 ![Link do wideo](../vsto/media/playvideo.gif "link do wideo") powiązane demonstracyjne wideo – zobacz [jak I: dostępu i manipulowania niestandardowe właściwości dokumentu w programie Microsoft Word?](http://go.microsoft.com/fwlink/?LinkId=136772).  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
## <a name="set-document-properties-in-excel"></a>Ustawianie właściwości dokumentu w programie Excel  
 Aby pracować z wbudowanych właściwości w programie Excel, należy użyć następujących właściwości:  
  
-   W projekcie na poziomie dokumentu, należy użyć <xref:Microsoft.Office.Tools.Excel.Workbook.BuiltinDocumentProperties%2A> właściwość `ThisWorkbook` klasy.  
  
-   W projekcie dodatku narzędzi VSTO dla programów, należy użyć <xref:Microsoft.Office.Interop.Excel._Workbook.BuiltinDocumentProperties%2A> właściwość <xref:Microsoft.Office.Interop.Excel.Workbook> obiektu.  
  
 Te właściwości zwracają <xref:Microsoft.Office.Core.DocumentProperties> obiektu, który jest kolekcją z <xref:Microsoft.Office.Core.DocumentProperty> obiektów. Możesz użyć `Item` właściwość kolekcji można pobrać określonej właściwości według nazwy lub indeksu w tej kolekcji.  
  
 Poniższy przykład kodu pokazuje, jak zmienić wbudowane **numer poprawki** właściwość w projekcie na poziomie dokumentu.  
  
### <a name="to-change-the-revision-number-property-in-excel"></a>Aby zmienić właściwość numer wersji w programie Excel  
  
1.  Właściwości dokumentu wbudowanych można przypisać do zmiennej.  
  
     [!code-vb[Trin_VstcoreProgramming#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#7)]
     [!code-csharp[Trin_VstcoreProgramming#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#7)]  
  
2.  Inkrementacja `Revision Number` właściwość, według jedną.  
  
     [!code-vb[Trin_VstcoreProgramming#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#8)]
     [!code-csharp[Trin_VstcoreProgramming#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#8)]  
  
## <a name="set-document-properties-in-word"></a>Ustawianie właściwości dokumentu w programie Word  
 Aby pracować z wbudowanych właściwości w programie Word, użyj następujących właściwości:  
  
-   W projekcie na poziomie dokumentu, należy użyć <xref:Microsoft.Office.Tools.Word.Document.BuiltInDocumentProperties%2A> właściwość `ThisDocument` klasy.  
  
-   W projekcie dodatku narzędzi VSTO dla programów, należy użyć <xref:Microsoft.Office.Interop.Word._Document.BuiltInDocumentProperties%2A> właściwość <xref:Microsoft.Office.Interop.Word.Document> obiektu.  
  
 Te właściwości zwracają <xref:Microsoft.Office.Core.DocumentProperties> obiektu, który jest kolekcją z <xref:Microsoft.Office.Core.DocumentProperty> obiektów. Możesz użyć `Item` właściwość kolekcji można pobrać określonej właściwości według nazwy lub indeksu w tej kolekcji.  
  
 Poniższy przykład kodu pokazuje, jak zmienić wbudowane **podmiotu** właściwość w projekcie na poziomie dokumentu.  
  
### <a name="to-change-the-subject-property"></a>Aby zmienić właściwość podmiotu  
  
1.  Właściwości dokumentu wbudowanych można przypisać do zmiennej.  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#1)]  
  
2.  Zmiana `Subject` właściwość "Oficjalny dokument".  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#2)]  
  
## <a name="robust-programming"></a>Skuteczne programowanie  
 W przykładach założono, że kod zostały napisane `ThisWorkbook` klasy w projekcie poziomie dokumentu dla programu Excel, a `ThisDocument` klasy w projekcie poziomie dokumentu dla programu Word.  
  
 Mimo że pracujesz z programu Word, Excel i w nich obiekty, Microsoft Office dostarcza listę właściwości dostępnych wbudowanych dokumentu. Podjęto próbę uzyskania dostępu do niezdefiniowanej właściwości zgłasza wyjątek.  
  
## <a name="see-also"></a>Zobacz także  
 [Program dodatków narzędzi VSTO](../vsto/programming-vsto-add-ins.md)   
 [Program dostosowań na poziomie dokumentu](../vsto/programming-document-level-customizations.md)   
 [Porady: tworzenie i modyfikowanie właściwości niestandardowego dokumentu](../vsto/how-to-create-and-modify-custom-document-properties.md)  
  
  