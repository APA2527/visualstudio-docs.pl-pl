---
title: 'Instrukcje: programowe ukrywanie arkuszy'
description: Dowiedz się, jak można programowo pokazać lub ukryć dowolny arkusz w skoroszycie programu Microsoft Excel przy użyciu elementu hosta arkusza.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden worksheets
- worksheets, hiding
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 5763e040e0206272b6b50b039f1260bcbc99db49
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99908596"
---
# <a name="how-to-programmatically-hide-worksheets"></a>Instrukcje: programowe ukrywanie arkuszy
  Możesz pokazać lub ukryć dowolny arkusz w skoroszycie. Aby ukryć arkusz, użyj elementu hosta arkusza lub uzyskaj dostęp do arkusza przy użyciu kolekcji arkusze skoroszytu.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="use-the-worksheet-host-item"></a>Użyj elementu hosta arkusza
 Jeśli arkusz został dodany w czasie projektowania w dostosowaniu na poziomie dokumentu, użyj <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> właściwości, aby ukryć określony arkusz.

### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Aby ukryć arkusz przy użyciu elementu hosta arkusza

1. Ustaw <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> Właściwość `Sheet1` elementu hosta na <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> wartość wyliczenia.

     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]

## <a name="use-the-sheets-collection-of-the-excel-workbook"></a>Korzystanie z kolekcji arkuszy skoroszytu programu Excel
 Dostęp do arkuszy za pomocą kolekcji programu Excel Microsoft Office <xref:Microsoft.Office.Interop.Excel.Sheets> w następujących przypadkach:

- Chcesz ukryć arkusz w dodatku narzędzi VSTO.

- Arkusz, który ma zostać ukryty, został utworzony w czasie wykonywania w dostosowaniu na poziomie dokumentu.

### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Aby ukryć arkusz przy użyciu kolekcji arkusze skoroszytu programu Excel

1. Ustaw <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> Właściwość arkusza na <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> wartość wyliczenia.

     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]

## <a name="see-also"></a>Zobacz też
- [Pracuj z arkuszami](../vsto/working-with-worksheets.md)
- [Instrukcje: programowe usuwanie arkuszy ze skoroszytów](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)
- [Instrukcje: Programowane przenoszenie arkuszy w skoroszytach](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)
- [Instrukcje: programowe Włączanie ochrony arkuszy](../vsto/how-to-programmatically-protect-worksheets.md)
- [Elementy hosta i formanty hosta — Omówienie](../vsto/host-items-and-host-controls-overview.md)
- [Globalny dostęp do obiektów w projektach pakietu Office](../vsto/global-access-to-objects-in-office-projects.md)
