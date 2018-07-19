---
title: Nie można usunąć wybranej klasy, ponieważ jest ona używana jako zwracany typ przez co najmniej jedną metodę DataContext
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 21ef0f86d701c899328044a03cde8035a1e7292d
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174214"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>Nie można usunąć wybranej klasy, ponieważ jest ona używana jako zwracany typ przez co najmniej jedną metodę DataContext

Typ zwracany co najmniej jeden <xref:System.Data.Linq.DataContext> metody jest klasą wybranej jednostki. Usuwanie klasę jednostki, która jest używana jako typ zwracany dla <xref:System.Data.Linq.DataContext> metoda powoduje, że kompilacja projektu nie powiedzie się. Aby usunąć klasy wybranej jednostki, określ <xref:System.Data.Linq.DataContext> metody, które go używać i ustawiać zwracanym typem klasy innej jednostki.

Aby przywrócić typów zwracanych <xref:System.Data.Linq.DataContext> metody służące do ich oryginalnej typów generowanych automatycznie, należy najpierw usunąć <xref:System.Data.Linq.DataContext> metody z **metody** okienka, a następnie przeciągnij obiekt z **Eksploratora serwera** / **Eksplorator bazy danych** na **O/R Designer** ponownie.

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Identyfikowanie <xref:System.Data.Linq.DataContext> metody, które używają klas jednostek jako zwracany typ, wybierając <xref:System.Data.Linq.DataContext> method in Class metoda **metody** okienka i zapoznanie się **typie zwracanym** właściwość **Właściwości** okna.

2. Ustaw **typie zwracanym** do klasy innej jednostki lub usuń <xref:System.Data.Linq.DataContext> metody z okienko metod.

## <a name="see-also"></a>Zobacz także

- [Komunikaty narzędzia Object Relational Designer](../data-tools/o-r-designer-messages.md)
- [Narzędzi LINQ to SQL w programie Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)