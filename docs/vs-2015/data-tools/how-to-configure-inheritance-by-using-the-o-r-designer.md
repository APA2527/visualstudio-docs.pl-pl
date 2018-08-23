---
title: 'Porady: Konfigurowanie dziedziczenia przy użyciu projektanta O R | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e594af12-e777-434a-bc08-7dd2dac84cdc
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ccfbd40fd9fd62921ff6f0661f87dca2995ae8fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696882"
---
# <a name="how-to-configure-inheritance-by-using-the-or-designer"></a>Porady: Konfigurowanie dziedziczenia za pomocą Projektanta obiektów relacyjnych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [jak: Konfigurowanie dziedziczenia przy użyciu projektanta O R](https://docs.microsoft.com/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).  
  
  
[!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) Obsługuje dziedziczenia pojedynczej tabeli, co jest często stosowana w systemach relacyjnych. Dziedziczenie pojedynczej tabeli Brak tabeli pojedynczej bazy danych, która zawiera pola zarówno informacje nadrzędnego, jak i podrzędnych. Z danymi relacyjnymi kolumna dyskryminatora zawiera wartość, która określa, która klasa dowolnego rekordu, o których należy.  
  
 Na przykład rozważmy tabelę osoby, która zawiera wszystkich stosowanych przez firmę. Niektórzy użytkownicy są pracownicy i niektóre osoby menedżerów. Tabela osób zawiera kolumnę o nazwie `EmployeeType` , ma wartość 1 dla menedżerów i wartość 2 dla pracowników; jest to kolumna dyskryminatora. W tym scenariuszu możesz utworzyć podklasę pracowników i wypełnić klasy za pomocą tylko te rekordy, które mają `EmployeeType` wartość 2. Z każdą z klas, można również usunąć kolumny, które nie mają zastosowania.  
  
 Tworzenie modelu obiektu, która korzysta z dziedziczenia (odpowiada relacyjnej bazie danych) może być nieco mylące. Poniższa procedura zawiera opis kroków wymaganych do konfigurowania dziedziczenie za pomocą Projektanta obiektów relacyjnych. Następujące ogólne kroki bez odwołujące się do istniejącej tabeli i kolumn może być trudne, dlatego podano wskazówki, która korzysta z danych. Aby uzyskać szczegółowe informacje krok po kroku dotyczące konfigurowania dziedziczenie za pomocą [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], zobacz [wskazówki: Tworzenie klasy programu LINQ to SQL przez dziedziczenie za pomocą pojedynczej tabeli (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md).  
  
### <a name="to-create-inherited-data-classes"></a>Do tworzenia klas danych dziedziczonych  
  
1.  Otwórz [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] , dodając **klasy LINQ do SQL** element do istniejącego projektu języka Visual Basic lub C#.  
  
2.  Przeciągnij tabelę, której chcesz użyć jako klasa bazowa na [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
3.  Przeciągnij drugiej kopii tabeli do [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] i zmień jego nazwę. Jest to klasa pochodna, lub podklasę.  
  
4.  Kliknij przycisk **dziedziczenia** w **Object Relational Designer** karcie **przybornika**, a następnie kliknij podklasy (tabela, nazwa została zmieniona) i połącz go z klasy bazowej.  
  
    > [!NOTE]
    >  Kliknij przycisk **dziedziczenia** pozycja **przybornika** i zwolnij przycisk myszy, kliknij drugą kopię klasy utworzonego w kroku 3, a następnie kliknij pierwszą klasą utworzony w kroku 2. Pierwsza klasa będzie wskazywać symbolu strzałki na linii dziedziczenia.  
  
5.  W każdej klasy należy usunąć wszystkie właściwości obiektu, które nie mają być wyświetlane i które nie są używane do skojarzenia. Zostanie wyświetlony błąd, jeśli użytkownik podejmie próbę usunięcia właściwości obiektu, używany do skojarzenia: [właściwość \<nazwa właściwości > nie można usunąć, ponieważ uczestniczy w skojarzeniu \<Nazwa skojarzenia >](../data-tools/the-property-property-name-cannot-be-deleted-because-it-is-participating-in-the-association-association-name.md).  
  
    > [!NOTE]
    >  Ponieważ klasa pochodna dziedziczy właściwości zdefiniowane w swojej klasie bazowej, te same kolumny nie można zdefiniować w każdej klasie. (Kolumny są implementowane jako właściwości). Tworzenie kolumny w klasie pochodnej można włączyć, ustawiając modyfikator dziedziczenia we właściwości w klasie bazowej. Aby uzyskać więcej informacji, zobacz [NOT IN kompilacji: zastępowanie właściwości i metody](http://msdn.microsoft.com/en-us/2167e8f5-1225-4b13-9ebd-02591ba90213).  
  
6.  Zaznacz wiersz dziedziczenia w [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
7.  W **właściwości** oknie **właściwość rozróżniacza** na nazwę kolumny, która służy do rozróżnienia rekordów w Twoich zajęciach.  
  
8.  Ustaw **wartość dyskryminatora klasy pochodnej** właściwości do wartości w bazie danych, która określa rekord jako typ dziedziczone. (Jest to wartość przechowywaną w kolumna dyskryminatora i służący do wyznaczenia odziedziczoną klasę).  
  
9. Ustaw **wartości dyskryminator klasy bazowej** właściwości wartość, która określa rekord jako typu podstawowego. (Jest to wartość przechowywaną w kolumna dyskryminatora i służący do wyznaczenia klasy podstawowej).  
  
10. Opcjonalnie możesz również ustawić **domyślne dziedziczenie** właściwość, aby wskazać typ w hierarchii dziedziczenia, która jest używana podczas ładowania wierszy, które nie pasują zdefiniowany kod dziedziczenia. Innymi słowy, jeśli rekord ma wartość w jej kolumna dyskryminatora, odpowiada wartości w jednym **wartość dyskryminatora klasy pochodnej** lub **wartość dyskryminatora klasy podstawowej** właściwości, rekord zostanie załadowany do typu wyznaczony jako **domyślne dziedziczenie**.  
  
## <a name="see-also"></a>Zobacz też  
 [LINQ to SQL Tools w programie Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Wskazówki: Tworzenie składnika LINQ to SQL klas (Projektant O-R)](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [PAVE What's New do tworzenia aplikacji danych w programie Visual Studio 2012](http://msdn.microsoft.com/en-us/3d50d68f-5f44-4915-842f-6d42fce793f1)   
 [Uzyskiwanie dostępu do danych w programie Visual Studio](../data-tools/accessing-data-in-visual-studio.md)   
 [LINQ do SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Wskazówki: Tworzenie klasy LINQ do SQL za pomocą pojedynczej tabeli dziedziczenia (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
 [NIE w kompilacji: Dziedziczenie w języku Visual Basic](http://msdn.microsoft.com/en-us/e5e6e240-ed31-4657-820c-079b7c79313c)   
 [Dziedziczenie](http://msdn.microsoft.com/library/81d64ee4-50f9-4d6c-a8dc-257c348d2eea)

