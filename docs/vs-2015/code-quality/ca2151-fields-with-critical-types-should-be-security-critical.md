---
title: 'CA2151: Pola typu krytycznego powinny być bezpieczne-krytyczne | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3eac6419ed443e2d3f9346e3d68936bc191b1752
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902805"
---
# <a name="ca2151-fields-with-critical-types-should-be-security-critical"></a>CA2151: Pola typu krytycznego powinny być bezpieczne-krytyczne
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2151: pola typu krytycznego powinny być bezpieczne-krytyczne](https://docs.microsoft.com/visualstudio/code-quality/ca2151-fields-with-critical-types-should-be-security-critical).

|||
|-|-|
|TypeName||
|CheckId|CA2151|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Pole przezroczyste zabezpieczeń lub bezpieczne-krytyczne jest zadeklarowane. Jego typ jest określony jako krytyczny pod względem zabezpieczeń. Na przykład:

```csharp
[assembly: AllowPartiallyTrustedCallers]

   [SecurityCritical]
   class Type1 { } // Security Critical type

   class Type2 // Security transparent type
   {
      Type1 m_field; // CA2151, transparent field of critical type
   }

```

 W tym przykładzie `m_field` jest polem przezroczystym zabezpieczeń typu, który jest krytyczny dla bezpieczeństwa.

## <a name="rule-description"></a>Opis reguły
 Aby używać typów krytycznych pod względem zabezpieczeń, kod odwołujący się do typu musi być albo krytyczny pod względem zabezpieczeń, albo bezpieczny-krytyczny pod względem zabezpieczeń. Ta zasada obowiązuje nawet w przypadku odwołania pośredniego. Na przykład w przypadku odwołania do pola przezroczystego, które ma typ krytyczny, kod musi być krytyczny pod względem zabezpieczeń lub bezpieczny pod względem zabezpieczeń. Dlatego pole mające zabezpieczenia przezroczyste lub pole bezpieczne-krytyczne pod względem zabezpieczeń jest mylące, ponieważ przezroczysty kod nadal nie będzie mógł uzyskać dostępu do pola.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, należy zaznaczyć pole z <xref:System.Security.SecurityCriticalAttribute> atrybut lub Ustaw typ, który odwołuje się do niej pole pod względem zabezpieczeń przezroczysty lub bezpieczny jako krytyczne.

```csharp
// Fix 1: Make the referencing field security critical
[assembly: AllowPartiallyTrustedCallers]

   [SecurityCritical]
   class Type1 { } // Security Critical type

   class Type2 // Security transparent type
   {
      [SecurityCritical]
      Type1 m_field; // Fixed: critical type, critical field
   }

// Fix 2: Make the referencing field security critical
[assembly: AllowPartiallyTrustedCallers]

   class Type1 { } // Type1 is now transparent

   class Type2 // Security transparent type
   {
      [SecurityCritical]
      Type1 m_field; // Fixed: critical type, critical field
   }

```

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2145.transparentmethodsshouldnotusesuppressunmanagedcodesecurity/cs/ca2145 - transparentmethodsshouldnotusesuppressunmanagedcodesecurity.cs#1)]

### <a name="comments"></a>Komentarze



