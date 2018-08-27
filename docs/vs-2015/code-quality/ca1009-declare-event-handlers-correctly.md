---
title: 'CA1009: Zadeklaruj poprawnie procedury obsługi zdarzeń | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b227e11f17a7a20ddf68b9a44317d965538bbab6
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900462"
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009: Należy poprawnie zadeklarować obsługę zdarzenia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1009: Zadeklaruj poprawnie procedury obsługi zdarzeń](https://docs.microsoft.com/visualstudio/code-quality/ca1009-declare-event-handlers-correctly).

|||
|-|-|
|TypeName|DeclareEventHandlersCorrectly|
|CheckId|CA1009|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Delegat, który obsługuje zdarzenie publiczne lub chronione nie ma poprawnej sygnatury zwracanego typu lub nazwy parametrów.

## <a name="rule-description"></a>Opis reguły
 Metody obsługi zdarzeń przyjmują dwa parametry. Pierwszy jest typu <xref:System.Object?displayProperty=fullName> i nosi nazwę "nadawca". Jest to obiekt, który wywołał zdarzenie. Drugi parametr jest typu <xref:System.EventArgs?displayProperty=fullName> i nosi nazwę "e". To dane, które są skojarzone ze zdarzeniem. Na przykład jeśli zdarzenie jest wywoływane zawsze wtedy, gdy plik jest otwarty, dane zdarzeń zwykle zawiera nazwę pliku.

 Metody obsługi zdarzeń powinny zwracać wartości. W języku programowania C#, jest to wskazywane przez zwracany typ `void`. Program obsługi zdarzeń można wywołać wiele metod w wielu obiektów. Jeśli zezwolono metod w celu zwrócenia wartości, z wieloma wartościami zwracanymi wystąpiłyby dla każdego zdarzenia, a wartość ostatniego metodę, która została wywołana będą dostępne.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, popraw sygnatury zwracanego typu i nazwy parametru delegata. Aby uzyskać szczegółowe informacje Zobacz poniższy przykład.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Poniższy przykład pokazuje delegata, który jest odpowiedni do obsługi zdarzeń. Metody, które może być wywoływany przez ten program obsługi zdarzeń są zgodne z podpisu, który jest określony w wytycznych projektowych. `AlarmEventHandler` jest nazwą typu delegata. `AlarmEventArgs` pochodzi z klasy bazowej dla danych zdarzeń <xref:System.EventArgs>, i przechowuje alarmu dane zdarzenia.

 [!code-cpp[FxCop.Design.EventsTwoParams#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/cpp/FxCop.Design.EventsTwoParams.cpp#1)]
 [!code-csharp[FxCop.Design.EventsTwoParams#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/cs/FxCop.Design.EventsTwoParams.cs#1)]
 [!code-vb[FxCop.Design.EventsTwoParams#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/vb/FxCop.Design.EventsTwoParams.vb#1)]

## <a name="related-rules"></a>Powiązane reguły
 [CA2109: Przejrzyj widoczne procedury obsługi zdarzeń](../code-quality/ca2109-review-visible-event-handlers.md)

## <a name="see-also"></a>Zobacz też
 <xref:System.EventArgs?displayProperty=fullName><xref:System.Object?displayProperty=fullName>
 [NIB: Zdarzenia i delegatów](http://msdn.microsoft.com/en-us/d98fd58b-fa4f-4598-8378-addf4355a115)



