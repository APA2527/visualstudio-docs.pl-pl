---
title: 'Instrukcje: Programowane dodawanie i usuwanie komentarzy do arkusza'
description: Dowiedz się, w jaki sposób można programowo dodawać i usuwać komentarze w Microsoft Office arkuszach programu Excel. Komentarze można dodawać tylko do pojedynczych komórek, a nie do zakresów wielokomórek.
ms.custom: SEO-VS-2020
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, comments
- worksheets, comments
- comments, worksheets
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: ec70c03dfdce05c7445762e2cfd452f3fdf90775
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99904496"
---
# <a name="how-to-programmatically-add-and-delete-worksheet-comments"></a>Instrukcje: Programowane dodawanie i usuwanie komentarzy do arkusza
  Można programowo dodawać i usuwać komentarze w Microsoft Office arkuszach programu Excel. Komentarze można dodawać tylko do pojedynczych komórek, a nie do zakresów wielokomórek.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="add-and-delete-a-comment-in-a-document-level-project"></a>Dodawanie i usuwanie komentarza w projekcie na poziomie dokumentu
 W poniższych przykładach założono, że istnieje jednokomórkowa <xref:Microsoft.Office.Tools.Excel.NamedRange> kontrolka o nazwie `dateComment` w arkuszu o nazwie `Sheet1` .

### <a name="to-add-a-new-comment-to-a-named-range"></a>Aby dodać nowy komentarz do nazwanego zakresu

1. Wywołaj <xref:Microsoft.Office.Tools.Excel.NamedRange.AddComment%2A> metodę <xref:Microsoft.Office.Tools.Excel.NamedRange> kontrolki i podaj tekst komentarza. Ten kod musi być umieszczony w `Sheet1` klasie.

     [!code-csharp[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#30)]

#### <a name="to-delete-a-comment-from-a-named-range"></a>Aby usunąć komentarz z nazwanego zakresu

1. Sprawdź, czy komentarz istnieje w zakresie i usuń go. Ten kod musi być umieszczony w `Sheet1` klasie.

     [!code-csharp[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#29)]

## <a name="add-and-delete-a-comment-in-a-vsto-add-in-project"></a>Dodawanie i usuwanie komentarza w projekcie dodatku narzędzi VSTO
 W poniższych przykładach założono, że <xref:Microsoft.Office.Interop.Excel.Range> w aktywnym arkuszu istnieje jedna komórka o nazwie `dateComment` .

### <a name="to-add-a-new-comment-to-an-excel-range"></a>Aby dodać nowy komentarz do zakresu programu Excel

1. Wywołaj <xref:Microsoft.Office.Interop.Excel.Range.AddComment%2A> metodę <xref:Microsoft.Office.Interop.Excel.Range> i podaj tekst komentarza.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#20)]

### <a name="to-delete-a-comment-from-an-excel-range"></a>Aby usunąć komentarz z zakresu programu Excel

1. Sprawdź, czy komentarz istnieje w zakresie i usuń go.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#19)]

## <a name="see-also"></a>Zobacz też
- [Pracuj z arkuszami](../vsto/working-with-worksheets.md)
- [Instrukcje: Programowane wyświetlanie komentarzy do arkusza](../vsto/how-to-programmatically-display-worksheet-comments.md)
- [NamedRange — formant](../vsto/namedrange-control.md)
