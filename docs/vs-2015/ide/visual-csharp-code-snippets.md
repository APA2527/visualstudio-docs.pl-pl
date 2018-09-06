---
title: Fragmenty kodu Visual C# | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snippets [C#], default snippets
- snippets [C#], Code Snippet Inserter
- Code Snippet Inserter [J#]
- Code Snippet Inserter [C#]
- Visual C#, default snippets
ms.assetid: dbea3dd6-e650-4190-b874-c9f097d7de6e
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2afbadccfc894dd5ba5baba9c58ab43417f44ed5
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2018
ms.locfileid: "43775443"
---
# <a name="visual-c-code-snippets"></a>Wstawki kodu Visual C#
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Visual C# — wstawki](https://docs.microsoft.com/visualstudio/ide/visual-csharp-code-snippets).  
  
Fragmenty kodu są gotowe fragmenty kodu, które szybko można wstawić w kodzie. Na przykład `for` fragment kodu tworzy pustą `for` pętli. Niektóre fragmenty kodu pochodzą z funkcji Otocz przez fragmenty kodu, które umożliwia wybór wierszy kodu, a następnie wybierz fragment kodu, która obejmuje też dokument wybranych wierszy kodu. Na przykład kiedy wybierz linii kodu i przy następnie uaktywnić `for` fragment kodu tworzy `for` pętli za pomocą tych wierszy kodu wewnątrz bloku pętli. Fragmenty kodu ułatwia pisanie program code szybsze, prostsze i bardziej niezawodne.  
  
 Wstaw fragment kodu w lokalizacji kursora lub Wstaw Otocz przez fragment kodu wokół zaznaczonego kodu. Wstawek kodu jest wywoływana za pomocą **Wstaw fragment kodu** lub **Otocz** polecenia na **IntelliSense** menu lub za pomocą skrótów klawiaturowych CTRL + K następnie X lub CTRL + K i następnie S odpowiednio.  
  
 Wstawek kodu wyświetla wszystkie dostępne wstawki programu nazwę fragmentu kodu. Wstawianie wstawek kodu obejmuje również okno dialogowe danych wejściowych, w którym możesz wpisać nazwę fragmentu kodu lub część nazwy fragmentu kodu. Wstawianie wstawek kodu wyróżnia najlepiej dopasowany do nazwy fragmentu kodu. Klawisza TAB w dowolnym momencie zamknąć wstawek kodu i Wstaw fragment kodu aktualnie wybrany. Wpisując ESC albo klikając przycisk myszy w edytorze kodu będą odrzucać wstawek kodu bez wstawiania fragmentu kodu.  
  
## <a name="default-code-snippets"></a>Fragmenty kodu domyślnego  
 Domyślnie następujące fragmenty kodu są uwzględnione w programie Visual Studio.  
  
|Nazwa (lub skrót)|Opis|Prawidłowe lokalizacje, aby wstawić fragment kodu|  
|--------------------------|-----------------|---------------------------------------|  
|#if|Tworzy [#if](http://msdn.microsoft.com/library/48cabbff-ca82-491f-a56a-eeccd528c7c2) dyrektywy i [#endif](http://msdn.microsoft.com/library/6a5fca55-5aee-441f-86f6-1c99fbe9ec05) dyrektywy.|W dowolnym miejscu.|  
|#region|Tworzy [#region](http://msdn.microsoft.com/library/672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4) dyrektywy i [#endregion](http://msdn.microsoft.com/library/16099660-91b2-49e5-9646-77f9ef069526) dyrektywy.|W dowolnym miejscu.|  
|~|Tworzy destruktor klasy zawierającej.|Wewnątrz klasy.|  
|— atrybut|Tworzy oświadczenie dla klasy, która pochodzi od klasy <xref:System.Attribute>.|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw), klasy lub struktury.|  
|checked|Tworzy [zaznaczone](http://msdn.microsoft.com/library/718a1194-988d-48a3-b089-d6ee8bd1608d) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|class|Tworzy deklaracji klasy.|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw), klasy lub struktury.|  
|ctor|Tworzy konstruktora dla klasy zawierającej.|Wewnątrz klasy.|  
|cw|Tworzy wywołanie <xref:System.Console.WriteLine%2A>.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|do|Tworzy [czy](http://msdn.microsoft.com/library/50725f79-9ba6-4898-aa78-6e331568a1bb) `while` pętli.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|else|Tworzy [else](http://msdn.microsoft.com/library/d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|enum|Tworzy [wyliczenia](http://msdn.microsoft.com/library/bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c) deklaracji.|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw), klasy lub struktury.|  
|equals|Tworzy deklaracji metody, która zastępuje <xref:System.Object.Equals%2A> metody zdefiniowanej w <xref:System.Object> klasy.|Wewnątrz klasy lub struktury.|  
|wyjątek|Tworzy oświadczenie dla klasy, która wynika z wyjątku (<xref:System.Exception> domyślnie).|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw), klasy lub struktury.|  
|dla|Tworzy [dla](http://msdn.microsoft.com/library/34041a40-2c87-467a-9ffb-a0417d8f67a8) pętli.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|foreach|Tworzy [foreach](http://msdn.microsoft.com/library/5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec) pętli.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|lepiej wykorzystać możliwości|Tworzy [dla](http://msdn.microsoft.com/library/34041a40-2c87-467a-9ffb-a0417d8f67a8) pętli tego zmniejsza zmienna pętli po każdej iteracji.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|if|Tworzy [Jeśli](http://msdn.microsoft.com/library/d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|Indeksator|Tworzy deklaracji indeksatora.|Wewnątrz klasy lub struktury.|  
|interface|Tworzy [interfejsu](http://msdn.microsoft.com/library/7da38e81-4f99-4bc5-b07d-c986b687eeba) deklaracji.|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw), klasy lub struktury.|  
|wywołania|Tworzy blok, który bezpiecznie wywołuje zdarzenie.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|iterator|Tworzy iterator.|Wewnątrz klasy lub struktury.|  
|iterindex|Tworzy "o nazwie" pary iteratora i indeksatora przy użyciu klasy zagnieżdżonej.|Wewnątrz klasy lub struktury.|  
|lock|Tworzy [blokady](http://msdn.microsoft.com/library/656da1a4-707e-4ef6-9c6e-6d13b646af42) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|mbox|Tworzy wywołanie <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>. Może trzeba dodać odwołanie do pliku System.Windows.Forms.dll.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|— przestrzeń nazw|Tworzy [przestrzeni nazw](http://msdn.microsoft.com/library/0a788423-9110-42e0-97d9-bda41ca4870f) deklaracji.|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw).|  
|Prop|Tworzy [automatycznie implementowana właściwość](http://msdn.microsoft.com/library/aa55fa97-ccec-431f-b5e9-5ac789fd32b7) deklaracji.|Wewnątrz klasy lub struktury.|  
|propfull|Tworzy deklaracja właściwości get i ustaw metody dostępu.|Wewnątrz klasy lub struktury.|  
|propg|Tworzy tylko do odczytu [automatycznie implementowana właściwość](http://msdn.microsoft.com/library/aa55fa97-ccec-431f-b5e9-5ac789fd32b7) za pomocą prywatnej metody dostępu "set".|Wewnątrz klasy lub struktury.|  
|SIM|Tworzy [statyczne](http://msdn.microsoft.com/library/5509e215-2183-4da3-bab4-6b7e607a4fdf)[int](http://msdn.microsoft.com/library/212447b4-5d2a-41aa-88ab-84fe710bdb52) deklaracji metody Main.|Wewnątrz klasy lub struktury.|  
|struktura |Tworzy [struktury](http://msdn.microsoft.com/library/ff3dd9b7-dc93-4720-8855-ef5558f65c7c) deklaracji.|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw), klasy lub struktury.|  
|svm|Tworzy [statyczne](http://msdn.microsoft.com/library/5509e215-2183-4da3-bab4-6b7e607a4fdf)[void](http://msdn.microsoft.com/library/0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4) deklaracji metody Main.|Wewnątrz klasy lub struktury.|  
|— przełącznik|Tworzy [Przełącz](http://msdn.microsoft.com/library/44bae8b8-8841-4d85-826b-8a94277daecb) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|Wypróbuj|Tworzy [try-catch —](http://msdn.microsoft.com/library/cb5503c7-bfa1-4610-8fc2-ddcd2e84c438) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|tryf|Tworzy [try-finally](http://msdn.microsoft.com/library/c27623fb-7261-4464-862c-7a369d3c8f0a) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|unchecked|Tworzy [unchecked](http://msdn.microsoft.com/library/0c021f7c-923f-4b3d-a58f-55336f5ac27e) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|unsafe|Tworzy [niebezpieczne](http://msdn.microsoft.com/library/7e818009-1c6e-4b9e-b769-3728a01586a0) bloku.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
|korzystanie|Tworzy [przy użyciu](http://msdn.microsoft.com/library/b42b8e61-5e7e-439c-bb71-370094b44ae8) dyrektywy.|Wewnątrz przestrzeni nazw (w tym globalnej przestrzeni nazw).|  
|while|Tworzy [podczas](http://msdn.microsoft.com/library/72a0765c-6852-4aca-b327-4a11cb7f5c59) pętli.|Wewnątrz metody, indeksatora, metody dostępu właściwości lub metody dostępu zdarzeń.|  
  
## <a name="see-also"></a>Zobacz też  
 [Funkcje wstawek kodu](../ide/code-snippet-functions.md)   
 [Fragmenty kodu](../ide/code-snippets.md)   
 [Porady: Tworzenie nowego fragmentu kodu przy użyciu zamiany](http://msdn.microsoft.com/en-us/8d56d43c-097a-475b-aa85-cae1554b6338)   
 [Parametry szablonu](../ide/template-parameters.md)   
 [Porady: użycie fragmentów kodu polecenia Otocz przez](../ide/how-to-use-surround-with-code-snippets.md)   
 [Instrukcje: przywracanie refaktoryzowanych wstawek kodu C#](../ide/how-to-restore-csharp-refactoring-snippets.md)



