---
title: 'Instrukcje: programowe otwieranie plików tekstowych jako skoroszytów'
description: Dowiedz się, jak za pomocą programu Visual Studio programowo otworzyć plik tekstowy jako skoroszyt programu Microsoft Excel.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 47582718128fc9818bb42571e3f33c0190a32d9e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99888748"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Instrukcje: programowe otwieranie plików tekstowych jako skoroszytów
  Plik tekstowy można otworzyć jako skoroszyt. Musisz przekazać nazwę pliku tekstowego, który chcesz otworzyć. Można określić kilka parametrów opcjonalnych, takich jak numer wiersza, od którego należy rozpocząć analizowanie, oraz format kolumny danych w pliku.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Przykład
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>Kompiluj kod
 W tym przykładzie wymagane są następujące składniki:

- Rozdzielany przecinkami plik tekstowy o nazwie zawierający `Test.txt` co najmniej trzy wiersze tekstu.

- Plik tekstowy, `Test.txt` który ma być przechowywany na dysku C.

## <a name="see-also"></a>Zobacz też
- [Pracuj ze skoroszytami](../vsto/working-with-workbooks.md)
- [Instrukcje: Programowane otwieranie skoroszytów](../vsto/how-to-programmatically-open-workbooks.md)
- [Instrukcje: Programowane tworzenie nowych skoroszytów](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Instrukcje: programowe zapisywanie skoroszytów](../vsto/how-to-programmatically-save-workbooks.md)
- [Instrukcje: programowe zamykanie skoroszytów](../vsto/how-to-programmatically-close-workbooks.md)
- [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)
