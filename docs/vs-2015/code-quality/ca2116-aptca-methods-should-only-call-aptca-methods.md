---
title: 'CA2116: Metody z atrybutem APTCA powinny wywoływać tylko metody z atrybutem APTCA | Dokumentacja firmy Microsoft'
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
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 78e3136ed2671de2962ae4de994bae178fcbceca
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902139"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116: Metody APTCA powinny wywoływać tylko metody APTCA
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2116: metody z atrybutem APTCA powinny wywoływać tylko metody z atrybutem APTCA](https://docs.microsoft.com/visualstudio/code-quality/ca2116-aptca-methods-should-only-call-aptca-methods).

|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda w zestawie przy użyciu <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> atrybut wywołuje metodę w zestawie, który nie ma atrybutu.

## <a name="rule-description"></a>Opis reguły
 Domyślnie metody publiczne lub chronione w zestawy o silnych nazwach niejawnie są chronione przez [zapotrzebowania na łącza](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) pełne zaufanie; tylko w pełni zaufanych obiektów wywołujących mogą uzyskiwać dostęp do zestawu z silną nazwą. Zestawy o silnych nazwach oznaczone <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atrybutu (APTCA) nie mają tej ochrony. Ten atrybut wyłącza zapotrzebowania na łącza, udostępnienie zestawu obiektów wywołujących, które nie mają pełnego zaufania, na przykład kod wykonywany z intranetu lub Internetu.

 Gdy atrybut APTCA jest obecny w zestawie całkowicie zaufanym i wykonuje kod w innym zestawie, który nie zezwala na dostęp częściowo zaufanych wywołań, możliwe jest luki w zabezpieczeniach. Jeśli dwie metody `M1` i `M2` spełniać następujące warunki, złośliwe obiekty wywołujące za pomocą metody `M1` można pominąć zapotrzebowanie na łącza niejawne pełnego zaufania, który chroni `M2`:

-   `M1` Metoda publiczna zadeklarowano w pełni zaufanym zestawie, który ma atrybut APTCA.

-   `M1` wywołuje metodę `M2` poza `M1`w zestawie.

-   `M2`w zestawie nie ma atrybut aptca i w związku z tym, nie powinien być wykonywany przez lub w imieniu obiektów wywołujących, które są częściowo zaufany.

 Częściowo zaufany obiekt wywołujący `X` można wywołać metodę `M1`, powodując `M1` do wywołania `M2`. Ponieważ `M2` nie ma atrybut APTCA jej bezpośredniego obiektu wywołującego (`M1`) musi spełniać zapotrzebowania na łącza, aby uzyskać pełne zaufanie; `M1` relacją pełnego zaufania i w związku z tym spełnia to sprawdzenie. To zagrożenie bezpieczeństwa, ponieważ `X` nie uczestniczy w spełnia żądanie łącza, które chroni `M2` z niezaufanych wywołujących. W związku z tym metody z atrybutem APTCA nie mogą wywoływać metody, które nie mają atrybutu.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Jeśli atrybut APCTA jest wymagana, należy używać żądanie do ochrony metodę, która wywołuje zestawów pełnego zaufania. Uprawnienia można żądanie będzie zależeć od funkcji udostępnianych przez metodę. Jeśli jest to możliwe, należy chronić metody żądanie, aby uzyskać pełne zaufanie upewnić się, że podstawową funkcjonalność nie jest narażony na częściowo zaufanych wywołań. Jeśli nie jest to możliwe, wybierz zestaw uprawnień wydajnie chroni narażonych funkcji. Aby uzyskać więcej informacji na temat wymagań, zobacz [zapotrzebowanie](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48).

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Aby bezpiecznie pominąć ostrzeżenie od tej reguły, upewnij się, czy funkcje udostępniane przez metodę bezpośrednio lub pośrednio uniemożliwia wywołującym uzyskania dostępu do poufnych informacji, operacji lub zasobów, które mogą być używane w szkodliwy sposób.

## <a name="example"></a>Przykład
 W poniższym przykładzie użyto dwa zestawy, a aplikacja testowa, aby zilustrować luki w zabezpieczeniach wykryte przez tę regułę. Pierwszy zestaw nie ma atrybut aptca i nie powinny być dostępne dla częściowo zaufanych wywołań (reprezentowane przez `M2` w poprzednim dyskusji).

 [!code-csharp[FxCop.Security.NoAptca#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.NoAptca/cs/FxCop.Security.NoAptca.cs#1)]

## <a name="example"></a>Przykład
 Drugi zestaw jest w pełni zaufany i umożliwia częściowo zaufanych wywołań (reprezentowane przez `M1` w poprzednim dyskusji).

 [!code-csharp[FxCop.Security.YesAptca#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.YesAptca/cs/FxCop.Security.YesAptca.cs#1)]

## <a name="example"></a>Przykład
 Aplikacja testowa (reprezentowane przez `X` w poprzednim dyskusji) jest częściowo zaufany.

 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TestAptcaMethods/cs/FxCop.Security.TestAptcaMethods.cs#1)]

 Ten przykład generuje następujące dane wyjściowe.

 **Wymaga, aby uzyskać pełne zaufanie: żądanie nie powiodło się. ** 
 **ClassRequiringFullTrust.DoWork została wywołana.**
## <a name="related-rules"></a>Powiązane reguły
 [CA2117: Typy z atrybutem APTCA powinny rozszerzać tylko typy podstawowe z atrybutem APTCA](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>Zobacz też
 [Wytyczne dotyczące bezpiecznego programowania](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) [zestawy .NET Framework wywoływane przez częściowo zaufany kod](http://msdn.microsoft.com/en-us/a417fcd4-d3ca-4884-a308-3a1a080eac8d) [używanie bibliotek pochodzących z częściowo zaufanego kodu](http://msdn.microsoft.com/library/dd66cd4c-b087-415f-9c3e-94e3a1835f74) [zapotrzebowanie](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48) [Link zapotrzebowanie](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) [dane i modelowanie](http://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)



