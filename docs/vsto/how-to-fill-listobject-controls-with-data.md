---
title: 'Instrukcje: wypełnianie kontrolek ListObject danymi'
description: Użyj powiązania danych, aby szybko dodać dane do dokumentu. Możesz również odłączyć obiekt listy, aby wyświetlał dane, ale nie jest już powiązany ze źródłem danych.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disconnecting from data sources
- ListObject control, disconnecting from a data source
- ListObject control, filling with data
- data [Office development in Visual Studio], adding to worksheets
- data binding, ListObject controls
- worksheets, populating with data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8ce2ef20b56a1803af5356137b798d83a5f1457f
ms.sourcegitcommit: ce85cff795df29e2bd773b4346cd718dccda5337
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "96846522"
---
# <a name="how-to-fill-listobject-controls-with-data"></a>Instrukcje: wypełnianie kontrolek ListObject danymi
  Możesz użyć powiązania danych, aby szybko dodać dane do dokumentu. Po powiązaniu danych z obiektem listy można odłączyć obiekt listy, aby wyświetlał dane, ale nie jest już powiązany ze źródłem danych.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

### <a name="to-bind-data-to-a-listobject-control"></a>Aby powiązać dane z kontrolką ListObject

1. Utwórz <xref:System.Data.DataTable> na poziomie klasy.

     [!code-csharp[Trin_VstcoreHostControlsExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#20)]
     [!code-vb[Trin_VstcoreHostControlsExcel#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#20)]

2. Dodaj przykładowe kolumny i dane do `Startup` procedury obsługi zdarzeń `Sheet1` klasy (w projekcie na poziomie dokumentu) lub `ThisAddIn` klasy (w projekcie na poziomie aplikacji).

     [!code-csharp[Trin_VstcoreHostControlsExcel#21](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#21)]
     [!code-vb[Trin_VstcoreHostControlsExcel#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#21)]

3. Wywołaj <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> metodę i przekaż nazwy kolumn w kolejności, w jakiej powinny się pojawiać. Kolejność kolumn w obiekcie list może się różnić od kolejności, w jakiej są wyświetlane w <xref:System.Data.DataTable> .

     [!code-csharp[Trin_VstcoreHostControlsExcel#22](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#22)]
     [!code-vb[Trin_VstcoreHostControlsExcel#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#22)]

### <a name="to-disconnect-the-listobject-control-from-the-data-source"></a>Aby odłączyć Formant ListObject ze źródła danych

1. Wywołaj <xref:Microsoft.Office.Tools.Excel.ListObject.Disconnect%2A> metodę `List1` .

     [!code-csharp[Trin_VstcoreHostControlsExcel#23](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#23)]
     [!code-vb[Trin_VstcoreHostControlsExcel#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#23)]

## <a name="compile-the-code"></a>Kompiluj kod
 W tym przykładzie kodu założono, że masz istniejącą <xref:Microsoft.Office.Tools.Excel.ListObject> nazwę `list1` w arkuszu, w którym znajduje się ten kod.

## <a name="see-also"></a>Zobacz także
- [Rozwiń dokumenty programu Word i skoroszyty programu Excel w dodatkach VSTO w czasie wykonywania](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Formanty w dokumentach pakietu Office](../vsto/controls-on-office-documents.md)
- [Dodawanie kontrolek do dokumentów pakietu Office w czasie wykonywania](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Instrukcje: Mapowanie kolumn ListObject na dane](../vsto/how-to-map-listobject-columns-to-data.md)
- [Automatyzowanie programu Excel za pomocą obiektów rozszerzonych](../vsto/automating-excel-by-using-extended-objects.md)
- [ListObject — formant](../vsto/listobject-control.md)
- [Powiązywanie danych z kontrolkami w rozwiązaniach pakietu Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Instrukcje: zapełnianie arkuszy danymi z bazy danych](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)
- [Instrukcje: zapełnianie dokumentów danymi z usług](../vsto/how-to-populate-documents-with-data-from-services.md)
