---
title: 'CA1303: Nie przekazuj literałów jako zlokalizowanych parametrów | Dokumentacja firmy Microsoft'
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
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2e86696970a9c53fe999054af0a762c200909525
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629581"
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303: Nie należy przekazywać literałów jako parametrów zlokalizowanych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1303: nie przekazuj literałów jako zlokalizowanych parametrów](https://docs.microsoft.com/visualstudio/code-quality/ca1303-do-not-pass-literals-as-localized-parameters).  
  
Element TypeName | DoNotPassLiteralsAsLocalizedParameters |  
| CheckId | CA1303 |  
| Kategoria | Microsoft.Globalization|  
| Zmiana powodująca niezgodność | Inne niż powodująca niezgodność |  
  
## <a name="cause"></a>Przyczyna  
 Metoda przekazuje ciąg literału jako parametr do konstruktora lub metody w [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] klasy biblioteki i ciąg ten powinien być możliwych do zlokalizowania.  
  
 To ostrzeżenie jest zgłaszane, gdy literał ciągu jest przekazywany jako wartość parametru lub właściwość dotyczy co najmniej jeden z następujących przypadkach:  
  
-   <xref:System.ComponentModel.LocalizableAttribute> Atrybut parametru lub właściwość jest ustawiona na wartość true.  
  
-   Nazwa parametru lub właściwości zawiera "Text", "Message" lub "Podpis".  
  
-   Nazwa parametru ciągu, który jest przekazywany do metody Console.Write — lub elementu Console.WriteLine jest "value" lub "format".  
  
## <a name="rule-description"></a>Opis reguły  
 Literały ciągów, które są osadzone w kodzie źródłowym są trudne do zlokalizowania.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby naprawić naruszenie tej zasady, Zamień literał ciągu pobierane w drodze wystąpienie <xref:System.Resources.ResourceManager> klasy.  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, jeśli nie jest lokalizowany biblioteki kodu lub jeśli ciąg nie jest uwidaczniana, aby użytkownik końcowy lub deweloperem, za pomocą biblioteki kodu.  
  
 Użytkownikom można wyeliminować szumu względem metod, które nie powinny być przekazywane zlokalizowanych ciągów, albo zmieniając nazwę parametru lub właściwość o nazwie lub oznaczając te elementy jako warunkowe.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia metodę, która zgłasza wyjątek, gdy jeden z dwóch argumentów są poza zakresem. Dla pierwszego argumentu konstruktora wyjątków jest przekazywany ciąg literału, który narusza tę regułę. Drugi argument Konstruktor poprawnie jest przekazywany ciąg, który został pobrany <xref:System.Resources.ResourceManager>.  
  
 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DoNotPassLiterals/cpp/FxCop.Globalization.DoNotPassLiterals.cpp#1)]
 [!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DoNotPassLiterals/cs/FxCop.Globalization.DoNotPassLiterals.cs#1)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Globalization.DoNotPassLiterals/vb/FxCop.Globalization.DoNotPassLiterals.vb#1)]  
  
## <a name="see-also"></a>Zobacz też  
 [Zasoby w aplikacjach klasycznych](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)



