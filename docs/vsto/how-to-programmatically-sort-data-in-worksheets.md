---
title: 'Porady: programowane sortowanie danych w arkuszach'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data sorting, worksheets
- data [Office development in Visual Studio], sorting in worksheets
- worksheets, sorting data
- sorting data, in worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1029ff61c7833ae03ab513ef486ecbd1edb1f295
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35676343"
---
# <a name="how-to-programmatically-sort-data-in-worksheets"></a>Porady: programowane sortowanie danych w arkuszach
  Można sortować dane znajdujące się na listach i zakresach arkusza w czasie wykonywania. Poniższy kod sortuje zakres wielokolumnowych o nazwie `Fruits` przez dane w pierwszej kolumnie, a następnie dane w drugiej kolumnie.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="sort-data-in-a-document-level-customization"></a>Sortowanie danych w dostosowaniu na poziomie dokumentu  
  
### <a name="to-sort-data-in-a-namedrange-control"></a>Aby posortować dane w kontrolki NamedRange  
  
1.  Wywołaj <xref:Microsoft.Office.Tools.Excel.NamedRange.Sort%2A> metody <xref:Microsoft.Office.Tools.Excel.NamedRange> kontroli. Poniższy przykład wymaga <xref:Microsoft.Office.Tools.Excel.NamedRange> formantu o nazwie `Fruits` w arkuszu. Ten kod muszą być umieszczone w klasie arkusza, nie w `ThisWorkbook` klasy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#78)]
     [!code-vb[Trin_VstcoreExcelAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#78)]  
  
 Umieść następujący kod w *Sheet1.vb* lub *Sheet1.cs* sortowania danych w <xref:Microsoft.Office.Tools.Excel.ListObject> kontroli. W kodzie założono, że masz <xref:Microsoft.Office.Tools.Excel.ListObject> formantu o nazwie `fruitList` w arkuszu o nazwie `Sheet1`.  
  
### <a name="to-sort-data-in-a-listobject-control"></a>Aby posortować dane w kontrolce ListObject  
  
1.  Wywołaj <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> metody <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> właściwość <xref:Microsoft.Office.Tools.Excel.ListObject> kontrolki hosta.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#79)]
     [!code-vb[Trin_VstcoreExcelAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#79)]  
  
## <a name="sort-data-in-a-vsto-add-in"></a>Sortowanie danych w dodatku narzędzi VSTO  
  
### <a name="to-sort-data-in-a-native-range"></a>Sortowanie danych w zakresie natywnych  
  
1.  Wywołaj <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> metody natywnej Excel <xref:Microsoft.Office.Interop.Excel.Range> kontroli. Poniższy przykład wymaga natywne kontrolki programu Excel o nazwie `Fruits` w arkuszu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#23](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#23](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#23)]  
  
### <a name="to-sort-data-in-a-listobject-control"></a>Aby posortować dane w kontrolce ListObject  
  
1.  Wywołaj <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> metody <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> właściwość natywnego programu Excel <xref:Microsoft.Office.Interop.Excel.ListObject> kontroli. W poniższym przykładzie założono, że masz natywne programu Excel <xref:Microsoft.Office.Interop.Excel.ListObject> formantu o nazwie `fruitList` w aktywnym arkuszu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#24](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#24](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#24)]  
  
## <a name="see-also"></a>Zobacz także  
 [Praca z arkuszami](../vsto/working-with-worksheets.md)   
 [Porady: programowane automatyczne wypełnienie zakresów przyrostowo zmieniającymi się danymi](../vsto/how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data.md)   
 [Porady: programowane odwoływanie do zakresów arkusza w kodzie](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Porady: programowane stosowanie stylów do zakresów arkusza w skoroszycie](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Namedrange — formant](../vsto/namedrange-control.md)   
 [ListObject — formant](../vsto/listobject-control.md)   
 [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  