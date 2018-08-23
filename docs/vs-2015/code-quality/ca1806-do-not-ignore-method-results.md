---
title: 'CA1806: Nie Ignoruj wyników metod | Dokumentacja firmy Microsoft'
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
- CA1806
- DoNotIgnoreMethodResults
helpviewer_keywords:
- CA1806
- DoNotIgnoreMethodResults
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c57d6622577fd0edd00354a6f2e211c973f1abb5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682265"
---
# <a name="ca1806-do-not-ignore-method-results"></a>CA1806: Nie ignoruj wyników metod
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotIgnoreMethodResults|  
|CheckId|CA1806|  
|Kategoria|Microsoft.Usage|  
|Zmiana kluczowa|Bez podziału|  
  
## <a name="cause"></a>Przyczyna  
 Istnieje kilka możliwych przyczyn tego ostrzeżenia:  
  
-   Nowy obiekt jest utworzony, ale nigdy używane.  
  
-   Wywoływana jest metoda, która tworzy i zwraca nowy ciąg, a nowy ciąg nigdy nie jest używany.  
  
-   Metody COM lub P/Invoke, która zwraca wartość HRESULT lub kodu błędu, który nigdy nie jest używany. Opis reguły  
  
 Tworzenie obiektów niepotrzebne i skojarzonych elementów bezużytecznych nieużywane obiektu obniżyć wydajność.  
  
 Ciągów są niezmienne i metod, takich jak String.ToUpper zwraca nowe wystąpienie ciągu zamiast modyfikowania wystąpienie ciągu w przypadku wywołania metody.  
  
 Ignorowanie HRESULT lub kod błędu może prowadzić do nieoczekiwanego zachowania w warunkach błędu lub warunki zasobów.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Jeśli metoda tworzy nowe wystąpienie obiektu B, który nie jest nigdy używana, przekaż wystąpienie jako argument do innej metody lub Przypisz wystąpienie do zmiennej. Jeśli tworzenie obiektów nie jest konieczne, usuń go.- lub -  
  
 Jeśli metoda wywołuje metodę B, ale nie używa nowego wystąpienia ciągu, które zwraca metoda B. Przekaż wystąpienie jako argument do innej metody, przypisz wystąpienie do zmiennej. Lub Usuń wywołanie funkcji, jeśli jest niepotrzebna.  
  
 —lub—  
  
 Jeśli metoda wywołuje metodę B, ale nie używa HRESULT lub kod błędu:, metoda zwraca. Użyj wyniku w instrukcji warunkowej, przypisz wynik do zmiennej lub przekaż go jako argument do innej metody.  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Nie pomijaj ostrzeżeń dla tej reguły, chyba że pełni niektóre funkcje, akt tworzenia obiektu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia klasę, która ignoruje wynik String.Trim wywoływania.  
  
<!-- TODO: review snippet reference  [!CODE [FxCop.Usage.DoNotIgnoreMethodResults#1](FxCop.Usage.DoNotIgnoreMethodResults#1)]  -->  
  
## <a name="example"></a>Przykład  
 Poniższy przykład naprawia wcześniejszego naruszenia praw przez przypisywanie wynik String.Trim zmienną, która została wywołana na.  
  
<!-- TODO: review snippet reference  [!CODE [FxCop.Usage.DoNotIgnoreMethodResults2#1](FxCop.Usage.DoNotIgnoreMethodResults2#1)]  -->  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia metodę, która nie korzysta z obiektu, który tworzy.  
  
> [!NOTE]
>  Nie można odtworzyć to naruszenie w języku Visual Basic.  
  
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults3/cpp/FxCop.Usage.DoNotIgnoreMethodResults3.cpp#1)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults3/cs/FxCop.Usage.DoNotIgnoreMethodResults3.cs#1)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults3/vb/FxCop.Usage.DoNotIgnoreMethodResults3.vb#1)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład naprawia wcześniejszego naruszenia praw przez usunięcie niepotrzebnych tworzenia obiektu.  
  
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults4/cpp/FxCop.Usage.DoNotIgnoreMethodResults4.cpp#1)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults4/cs/FxCop.Usage.DoNotIgnoreMethodResults4.cs#1)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults4/vb/FxCop.Usage.DoNotIgnoreMethodResults4.vb#1)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia metodę, która ignoruje metody natywnej GetShortPathName zwraca kod błędu.  
  
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults5/cpp/FxCop.Usage.DoNotIgnoreMethodResults5.cpp#1)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults5/cs/FxCop.Usage.DoNotIgnoreMethodResults5.cs#1)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład naprawia wcześniejszego naruszenia praw, sprawdzając kod błędu i zostanie zgłoszony wyjątek, gdy wywołanie nie powiodło się.  
  
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults6/cpp/FxCop.Usage.DoNotIgnoreMethodResults6.cpp#1)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults6/cs/FxCop.Usage.DoNotIgnoreMethodResults6.cs#1)]