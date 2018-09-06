---
title: 'Porady: programowane zamykanie skoroszytów'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, closing
- Excel [Office development in Visual Studio], closing workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 36b7da02830375161af08bda301e3ead98321741
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677471"
---
# <a name="how-to-programmatically-close-workbooks"></a>Porady: programowane zamykanie skoroszytów
  Możesz zamknąć aktywny skoroszyt, lub można określić skoroszytu, aby zamknąć.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="close-the-active-workbook"></a>Zamknij aktywny skoroszyt  
 Istnieją dwie procedury do zamykania aktywnym skoroszycie: jeden dla dostosowywania poziomie dokumentu i jeden dla dodatków narzędzi VSTO.  
  
### <a name="to-close-the-active-workbook-in-a-document-level-customization"></a>Aby zamknąć aktywnym skoroszycie w dostosowaniu na poziomie dokumentu  
  
1.  Wywołaj <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> metodę, aby zamknąć skoroszyt służącej do dostosowywania. Aby użyć w poniższym przykładzie kodu, należy uruchomić go `Sheet1` klasy w projekcie poziomie dokumentu dla programu Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#3)]  
  
### <a name="to-close-the-active-workbook-in-a-vsto-add-in"></a>Aby zamknąć aktywnym skoroszycie w dodatku narzędzi VSTO  
  
1.  Wywołaj <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> metodę, aby zamknąć aktywny skoroszyt. Aby użyć w poniższym przykładzie kodu, należy uruchomić go `ThisAddIn` klasy w projekcie dodatku narzędzi VSTO dla programu Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="close-a-workbook-that-you-specify-by-name"></a>Zamknij skoroszyt zawierający według nazwy  
 Sposób, w jaki Zamknij skoroszyt zawierający według nazwy jest taka sama dla dodatków narzędzi VSTO dla programów i dostosowań na poziomie dokumentu.  
  
### <a name="to-close-a-workbook-that-you-specify-by-name"></a>Aby zamknąć skoroszyt zawierający według nazwy  
  
1.  Określ nazwę skoroszytu jako argument do <xref:Microsoft.Office.Interop.Excel.Workbooks> kolekcji. Poniższy przykład kodu zakłada, że skoroszyt o nazwie **NewWorkbook** jest otwarty w programie Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="see-also"></a>Zobacz także  
 [Praca ze skoroszytami](../vsto/working-with-workbooks.md)   
 [Porady: programowane zapisywanie skoroszytów](../vsto/how-to-programmatically-save-workbooks.md)   
 [Porady: programowane otwieranie skoroszytów](../vsto/how-to-programmatically-open-workbooks.md)   
 [Ograniczenia programowe elementów hosta i kontrolek hosta](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Host formantów Przegląd obiektów hosta i](../vsto/host-items-and-host-controls-overview.md)  
  
  