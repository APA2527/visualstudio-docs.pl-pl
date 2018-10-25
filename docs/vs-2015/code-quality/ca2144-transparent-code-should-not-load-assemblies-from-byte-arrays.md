---
title: 'CA2144: Kod przezroczysty nie powinien ładować zestawów z tablic bajtowych | Dokumentacja firmy Microsoft'
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
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 395a21b7926f9b47a001eb3021026e27b3e4eb39
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49922799"
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: Jawny kod nie powinien ładować zestawów z tablic bajtowych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|
|CheckId|CA2144|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda przezroczysta pod względem ładuje zestaw z tablicy bajtowej przy użyciu jednej z następujących metod:

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

## <a name="rule-description"></a>Opis reguły
 Przegląd zabezpieczeń dla kodu przezroczystego nie jest tak dokładny jak kodu krytycznego pod względem bezpieczeństwa, ponieważ przezroczysty kod nie może wykonywać czynności wrażliwych pod względem bezpieczeństwa. Zestawy, ładowane z tablicy bajtowej, mogą nie być niezauważone w przezroczystym kodzie, a ta tablica bajtów może zawierać krytyczny albo, co ważniejsze, krytyczny dla bezpieczeństwa kod, który powinien być poddany inspekcji. W związku z tym kod przezroczysty nie powinien ładować zestawów z tablicy bajtowej.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy oznaczyć metody, która jest ładowana zestaw za pomocą <xref:System.Security.SecurityCriticalAttribute> lub <xref:System.Security.SecuritySafeCriticalAttribute> atrybutu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Reguła jest uruchamiana na następujący kod, ponieważ metoda przezroczysta pod względem ładuje zestaw z tablicy bajtowej.

 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2144.transparentmethodsshouldnotloadassembliesfrombytearrays/cs/ca2144 - transparentmethodsshouldnotloadassembliesfrombytearrays.cs#1)]



