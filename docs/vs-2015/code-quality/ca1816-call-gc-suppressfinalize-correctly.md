---
title: 'CA1816: Wywołaj GC. SuppressFinalize poprawnie | Dokumentacja firmy Microsoft'
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
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 27297a49cc2eedb4e7edd067ac639a699078ac7c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630977"
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816: Wywołaj poprawnie GC.SuppressFinalize
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1816: Wywołaj GC. SuppressFinalize poprawnie](https://docs.microsoft.com/visualstudio/code-quality/ca1816-call-gc-suppressfinalize-correctly).  
  
Element TypeName | CallGCSuppressFinalizeCorrectly |  
| CheckId | CA1816 |  
| Kategoria | Firmy Microsoft. Sposób użycia |  
| Zmiana powodująca niezgodność | Inne niż powodująca niezgodność |  
  
## <a name="cause"></a>Przyczyna  
  
-   Metody, która jest implementacją <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> nie mogą wywoływać <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
-   Metody, która nie jest implementacją <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> wywołania <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
-   Wywołuje metodę <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> i przekazuje na coś innego niż to (Me w języku Visual Basic).  
  
## <a name="rule-description"></a>Opis reguły  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> Metoda pozwala zwolnić zasoby w dowolnym momencie przed obiekt staje się dostępna dla wyrzucania elementów bezużytecznych. Jeśli <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> metoda jest wywoływana, zwalnia zasoby obiektu. To sprawia, że finalizacja niepotrzebne. <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> należy wywołać <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> więc moduł odśmiecania pamięci nie mogą wywoływać finalizatora obiektu.  
  
 Aby zapobiec typy pochodne z finalizatory mających potrzebę ponownego zaimplementowania interfejsu [System.IDisposable] (<!-- TODO: review code entity reference <xref:assetId:///System.IDisposable?qualifyHint=True&amp;autoUpgrade=False>  -->) i wywołać go, niezapieczętowane typy bez finalizatorów powinna nadal wywołać <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby naprawić naruszenie tej zasady:  
  
 Jeśli metoda jest implementacją <xref:System.IDisposable.Dispose%2A>, dodaj wywołanie do <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 Jeśli metoda nie jest implementacją <xref:System.IDisposable.Dispose%2A>, albo Usuń wywołanie funkcji <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> lub przenieść je na typ <xref:System.IDisposable.Dispose%2A> implementacji.  
  
 Zmień wszystkie wywołania do <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> do przekazania tego (Me w języku Visual Basic).  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Tylko Pomijaj ostrzeżeń dla tej reguły, jeśli są deliberating przy użyciu <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> kontrolować okres istnienia innych obiektów. Nie pomijaj ostrzeżeń dla tej reguły, jeśli implementacja <xref:System.IDisposable.Dispose%2A> nie mogą wywoływać <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>. W takiej sytuacji nie można wstrzymać finalizację spadku wydajności i zapewnia nie korzyści.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano metodę oznacza niepoprawnie wywołania <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly/CS/FxCop.Usage.CallGCSuppressFinalizeCorrectly.cs#1)]
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly/VB/FxCop.Usage.CallGCSuppressFinalizeCorrectly.vb#1)]  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano metodę, który prawidłowo wywołania <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly2/CS/FxCop.Usage.CallGCSuppressFinalizeCorrectly2.cs#1)]
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly2/VB/FxCop.Usage.CallGCSuppressFinalizeCorrectly2.vb#1)]  
  
## <a name="related-rules"></a>Powiązane reguły  
 [CA2215: Metody Dispose powinny wywoływać metodę Dispose klasy podstawowej](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA2216: Typy możliwe do likwidacji powinny deklarować finalizator](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Wzorzec Dispose](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)



