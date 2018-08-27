---
title: 'CA1304: Określ CultureInfo | Dokumentacja firmy Microsoft'
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
- SpecifyCultureInfo
- CA1304
helpviewer_keywords:
- SpecifyCultureInfo
- CA1304
ms.assetid: b912d76a-54fd-4c93-b25d-16491e0ae319
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 149ab03c1ee33d8aaf5aae30ddf56150279c4052
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42903037"
---
# <a name="ca1304-specify-cultureinfo"></a>CA1304: Określ CultureInfo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1304: Określ CultureInfo](https://docs.microsoft.com/visualstudio/code-quality/ca1304-specify-cultureinfo).

|||
|-|-|
|TypeName|SpecifyCultureInfo|
|CheckId|CA1304|
|Kategoria|Microsoft.Globalization|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Metoda lub Konstruktor wywołuje członka mającego przeciążenie, które akceptuje <xref:System.Globalization.CultureInfo?displayProperty=fullName> parametru, a metoda lub Konstruktor niewywołujący przeciążenia, które przyjmuje <xref:System.Globalization.CultureInfo> parametru. Ta zasada powoduje ignorowanie wywołania następujących metod:

-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>

## <a name="rule-description"></a>Opis reguły
 Gdy <xref:System.Globalization.CultureInfo> lub <xref:System.IFormatProvider?displayProperty=fullName> obiektu nie jest podany, wartość domyślna, która jest dostarczana przez członka przeciążonego może nie wywoływać oczekiwanego efektu we wszystkich ustawieniach regionalnych. Ponadto [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] członków wybierz domyślną kulturę i formatowanie na podstawie założeń, które mogą być niepoprawne w kodzie. Aby upewnić się, że kod działa zgodnie z oczekiwaniami dla scenariuszy, należy podać charakterystyczne dla kultury informacje zgodnie z następującymi wytycznymi:

-   Jeśli wartość będzie wyświetlana dla użytkownika, należy użyć bieżącej kultury. Zobacz <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.

-   Jeśli wartości są przechowywane i używane przez oprogramowanie, oznacza to, utrwalone w pliku lub bazy danych, użyć niezmiennej kultury. Zobacz <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.

-   Jeśli miejsce docelowe wartość nie jest znany, mają odbiorcy danych lub dostawca określenie kultury.

 Należy pamiętać, że <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> służy tylko do pobrania zlokalizowanych zasobów przy użyciu wystąpienia <xref:System.Resources.ResourceManager?displayProperty=fullName> klasy.

 Nawet jeśli domyślne zachowanie członka przeciążonego jest odpowiednia dla Twoich potrzeb, lepiej jest jawnie wywołać przeciążenie specyficzne dla kultury tak, aby Twój kod jest automatycznie dokumentowane i łatwiej utrzymywane w dobrym stanie.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, użyj przeciążenia, które przyjmuje <xref:System.Globalization.CultureInfo> lub <xref:System.IFormatProvider> i określić argument, zgodnie z wytycznymi, które zostały wymienione wcześniej.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, gdy jest pewne, że domyślny dostawca kultury/format jest odpowiednim wyborem oraz łatwości utrzymania kodu nie ma priorytet ważne rozwoju.

## <a name="example"></a>Przykład
 W poniższym przykładzie `BadMethod` powoduje, że dwa naruszenie tej zasady. `GoodMethod` Naprawia pierwszy naruszenia przez przekazanie niezmiennej kultury do System.String.Compare i usuwa drugi naruszenia przez przekazanie bieżącej kultury, aby <xref:System.String.ToLower%2A> ponieważ `string3` jest wyświetlany użytkownikowi.

 [!code-csharp[FxCop.Globalization.CultureInfo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.CultureInfo/cs/FxCop.Globalization.CultureInfo.cs#1)]

## <a name="example"></a>Przykład
 Poniższy przykład przedstawia efekt bieżącej kultury na domyślnym <xref:System.IFormatProvider> wybranego przez <xref:System.DateTime> typu.

 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.IFormatProvider/cs/FxCop.Globalization.IFormatProvider.cs#1)]

 Ten przykład generuje następujące dane wyjściowe.

 **6/4/1900 12:15:12 PM**
**06-04-1900 12:15:12**
## <a name="related-rules"></a>Powiązane reguły
 [CA1305: Określ interfejs IFormatProvider](../code-quality/ca1305-specify-iformatprovider.md)

## <a name="see-also"></a>Zobacz też
 [NIB: Używanie klasy CultureInfo](http://msdn.microsoft.com/en-us/d4329e34-64c3-4d1e-8c73-5b0ee626ba7a)



