---
title: 'CA1017: Oznacz zestawy atrybutem ComVisibleAttribute | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b5ce7d8a6bd63bc49a03661323ef17d131201cce
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49206950"
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: Oznacz zestawy za pomocą ComVisibleAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|MarkAssembliesWithComVisible|
|CheckId|CA1017|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Zestaw nie ma <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> zastosowany do niego.

## <a name="rule-description"></a>Opis reguły
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Atrybut określa, w jaki sposób klienci COM dostęp do kodu zarządzanego. Zasada dobrego projektowania nakazuje, aby zestawy jawnie wskazywały widoczność COM. Widoczność COM można ustawić dla całego zestawu i następnie zastąpić dla poszczególnych typów i elementów członkowskich typu. Jeśli ten atrybut nie jest obecny, zawartość zestawu są widoczne dla klientów modelu COM.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, Dodaj atrybut do zestawu. Jeśli nie chcesz, zestawów, które mają być widoczne dla klientów modelu COM, zastosuj atrybut i ustawić jej wartość na `false`.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły. Jeśli chcesz, aby zestaw był widoczny, zastosuj atrybut i ustawić jej wartość na `true`.

## <a name="example"></a>Przykład
 W poniższym przykładzie przedstawiono zestaw, który ma <xref:System.Runtime.InteropServices.ComVisibleAttribute> zastosowany do uniemożliwić jest widoczny dla klientów modelu COM.

 [!code-cpp[FxCop.Design.AssembliesCom#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cpp/FxCop.Design.AssembliesCom.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cs/FxCop.Design.AssembliesCom.cs#1)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/vb/FxCop.Design.AssembliesCom.vb#1)]

## <a name="see-also"></a>Zobacz też
 [Współdziałanie z niezarządzanego kodu](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258) [kwalifikowanie typów .NET do międzyoperacyjności](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)



