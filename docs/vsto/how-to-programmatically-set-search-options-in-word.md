---
title: 'Instrukcje: Programowane Ustawianie opcji wyszukiwania w programie Word'
description: Dowiedz się, jak można użyć programu Visual Studio do programistycznego ustawiania opcji wyszukiwania dla opcji wyboru w programie Microsoft Word.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- settings, Word search options
- documents [Office development in Visual Studio], search options
- Word, searching options
- searching, Word options
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: e583b7deb9fbe37f40e582d2c8a946332dd00ffa
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99913471"
---
# <a name="how-to-programmatically-set-search-options-in-word"></a>Instrukcje: Programowane Ustawianie opcji wyszukiwania w programie Word
  Istnieją dwa sposoby konfigurowania opcji wyszukiwania dla opcji w Microsoft Office dokumentach programu Word:

- Ustaw poszczególne właściwości <xref:Microsoft.Office.Interop.Word.Find> obiektu.

- Użyj argumentów <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metody <xref:Microsoft.Office.Interop.Word.Find> obiektu.

  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="use-properties-of-a-find-object"></a>Korzystanie z właściwości obiektu Find
 Poniższy kod ustawia właściwości <xref:Microsoft.Office.Interop.Word.Find> obiektu, aby wyszukać tekst w bieżącym zaznaczeniu. Zwróć uwagę, że kryteria wyszukiwania, takie jak wyszukiwanie w przód, zawijanie i tekst do wyszukania, są właściwościami <xref:Microsoft.Office.Interop.Word.Find> obiektu.

 Ustawienie każdej właściwości <xref:Microsoft.Office.Interop.Word.Find> obiektu nie jest przydatne podczas pisania kodu w języku C#, ponieważ należy określić te same właściwości jako parametry w <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metodzie. W związku z tym ten przykład zawiera tylko kod Visual Basic.

### <a name="to-set-search-options-using-a-find-object"></a>Aby ustawić opcje wyszukiwania przy użyciu obiektu Find

1. Ustaw właściwości <xref:Microsoft.Office.Interop.Word.Find> obiektu, aby przeszukiwać do przodu przez zaznaczenie tekstu **Znajdź mnie**.

     [!code-vb[Trin_VstcoreWordAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#76)]

## <a name="use-execute-method-arguments"></a>Użyj argumentów wykonywania metody
 Poniższy kod używa <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metody <xref:Microsoft.Office.Interop.Word.Find> obiektu do wyszukania tekstu w bieżącym zaznaczeniu. Zwróć uwagę, że kryteria wyszukiwania, takie jak wyszukiwanie w przód, zawijanie i tekst do wyszukania, są przekazywane jako parametry <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metody.

### <a name="to-set-search-options-using-execute-method-arguments"></a>Aby ustawić opcje wyszukiwania za pomocą argumentów metody Execute

1. Przekaż kryteria wyszukiwania jako parametry metody, <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> aby przeszukiwać do przodu przez zaznaczenie tekstu **Znajdź mnie**.

     [!code-vb[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#77)]
     [!code-csharp[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#77)]

## <a name="see-also"></a>Zobacz też
- [Instrukcje: programowe wyszukiwanie i zastępowanie tekstu w dokumentach](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
- [Instrukcje: programowe przechodzenie w pętli poprzez znalezione elementy w dokumentach](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)
- [Instrukcje: Programowane przywracanie zaznaczenia po wyszukiwaniu](../vsto/how-to-programmatically-restore-selections-after-searches.md)
