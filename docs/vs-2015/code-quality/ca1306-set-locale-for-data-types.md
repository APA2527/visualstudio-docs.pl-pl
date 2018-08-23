---
title: 'Ca1306: należy Ustawić ustawienia regionalne dla typów danych | Dokumentacja firmy Microsoft'
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
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6ece2ead5931f17b27ecdf86672df37b932ddefb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682737"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: Należy ustawić ustawienia regionalne dla typów danych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1306: Ustaw ustawienia regionalne dla typów danych](https://docs.microsoft.com/visualstudio/code-quality/ca1306-set-locale-for-data-types).  
  
Element TypeName | SetLocaleForDataTypes |  
| CheckId | CA1306 |  
| Kategoria | Microsoft.Globalization|  
| Zmiana powodująca niezgodność | Bez podziału |  
  
## <a name="cause"></a>Przyczyna  
 Metoda lub Konstruktor utworzony co najmniej jeden <xref:System.Data.DataTable?displayProperty=fullName> lub <xref:System.Data.DataSet?displayProperty=fullName> wystąpień i nie jawnie ustawiona właściwość locale (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> lub <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).  
  
## <a name="rule-description"></a>Opis reguły  
 Ustawienia regionalne określą elementy prezentacji charakterystyczne dla kultury dla danych, takich jak formatowanie używane dla wartości liczbowych, symbole walut i porządek sortowania. Po utworzeniu <xref:System.Data.DataTable> lub <xref:System.Data.DataSet>, należy jawnie ustawić ustawienia regionalne. Domyślnie ustawienia regionalne dla tych typów jest bieżącej kultury. Dla danych, które są przechowywane w bazie danych lub pliku i są udostępniane globalnie, ustawienia regionalne zazwyczaj powinna być ustawiona na niezmiennej kultury (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>). Gdy dane są dzielone między kultur, przy użyciu domyślnych ustawień regionalnych może spowodować zawartość <xref:System.Data.DataTable> lub <xref:System.Data.DataSet> mają być wyświetlone lub niepoprawnie interpretowane.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby naprawić naruszenie tej zasady, należy jawnie ustawić ustawienia regionalne <xref:System.Data.DataTable> lub <xref:System.Data.DataSet>.  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, biblioteka lub aplikacji jest ograniczona odbiorców lokalnych, danych nie jest udostępniony lub domyślne ustawienie daje żądane zachowanie we wszystkich obsługiwanych scenariuszach.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy dwie <xref:System.Data.DataTable> wystąpień.  
  
 [!code-csharp[FxCop.Globalization.DataTable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DataTable/cs/FxCop.Globalization.DataTable.cs#1)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Data.DataTable?displayProperty=fullName>   
 <xref:System.Data.DataSet?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>



