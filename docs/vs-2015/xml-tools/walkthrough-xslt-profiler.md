---
title: 'Wskazówki: Profiler XSLT | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87387c9a-2e89-4801-ad51-83740cd6ea25
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4f401d253c81385dc197e912a7f9cc7d6156e393
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49229453"
---
# <a name="walkthrough-xslt-profiler"></a>Przewodnik: profiler XSLT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Profiler XSLT tworzy szczegółowe raporty wydajności XSLT, które ułatwiają pomiar i docelowe problemy związane z wydajnością w kodzie XSLT i oceny. Profiler XSLT obejmuje, przydatne wskazówki dotyczące optymalizacji o arkusza stylów XSL i XSLT. Dla aplikacji XSLT tego żądanie uzyskania maksymalnej wydajności to narzędzie może być istotne.  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 Procedury przedstawione w następującym przewodniku wymaga programu Visual Studio 2010 and.NET Framework w wersji 4.0. Profiler XSLT jest dostępne tylko z Microsoft Visual Studio Team System z zainstalowanymi narzędziami profilowania.  
  
### <a name="create-the-performance-report"></a>Tworzenie raportu wydajności  
  
1.  Otwórz dokument XSLT, ale w programie Visual Studio.  
  
2.  Kliknij pozycję **XSLT profilu** opcja, która jest dostępna w XML menu.  
  
3.  Podaj wprowadź dokument XML. Jeśli dokument XML nie jest jeszcze otwarty, użytkownik jest monitowany dla pliku.  
  
4.  Analiza zostanie uruchomiony, pasek postępu wyświetlany postęp w edytorze.  
  
5.  Dane wyjściowe XSLT jest widoczny w okienku danych wyjściowych.  
  
6.  Po zakończeniu sesji wydajności, sprawdź raport o wydajności. Dane zapisane w raporcie wydajności pozwala przeglądać i analizować wydajność XSLT.  
  
### <a name="get-all-the-available-views"></a>Pobierz dostępne widoki  
  
1.  Kliknij pozycję **bieżący widok** listy rozwijanej, aby uzyskać wszystkie dostępne widoki.  
  
2.  Wybierz **Widok Podsumowanie** opcji **bieżący widok** listy rozwijanej. Domyślnie raport wydajności jest wyświetlana w **Widok Podsumowanie**. Ten widok jest punktem wyjścia do określenia problemów z wydajnością za pomocą dokumentów XSLT. **Widok Podsumowanie** Wyświetla następujących punktów danych:  
  
    -   Funkcje wywoływane najczęściej  
  
    -   Funkcje z największą ilością indywidualnej pracy  
  
    -   Funkcje zajmujące najwięcej czasu do wykonania  
  
3.  Domyślnie, istnieją trzy kolumny dla każdego punktu danych: Nazwa funkcji, liczba wywołań w wartościach bezwzględnych i wartość procentową o nazwie funkcji do wywołania całej funkcji. Z każdym danych do punktu w **Widok Podsumowanie**, możesz przejść do bardziej szczegółowych widoków przez kliknięcie prawym przyciskiem myszy punkty danych funkcji.  
  
4.  Wybierz **widoku funkcji** opcji **bieżący widok** listy rozwijanej. **Widoku funkcji** Wyświetla listę funkcji, wywoływany podczas profilowania. Dane można sortować, klikając nazwę kolumny. Kolumny domyślnie wyświetlane są:  
  
    -   **Nazwa funkcji**  
  
    -   **Całkowity czas, który upłynął**  
  
    -   **Czas wyłączny, który upłynął**  
  
    -   **Całkowity czas aplikacji**  
  
    -   **Własny czas aplikacji**  
  
    -   **Liczba wywołań**  
  
5.  Wszystkie kolumny godziny są wyświetlane zarówno w przypadku wartości bezwzględne, jak i wartości procentowe. Termin **wyłączne** odwołuje się do całkowitego czasu funkcji wykonywania zużyte, z wyłączeniem czasu poświęconego przez inne funkcje wywoływane podczas wykonywania tej funkcji.  
  
6.  Termin **włącznie** odwołuje się do całkowity czas funkcję wykonywania, w tym czas wykonywania wszystkich funkcji, o nazwie oraz tego, czy którakolwiek z tych nazywane funkcjami o nazwie innych funkcji.  
  
### <a name="select-callercallee-view"></a>Wybierz widok wywołujący/wywoływany  
  
1.  Wybierz **wywołujący/wywoływany** wyświetlać w **bieżący widok** listy rozwijanej.  
  
2.  **Wywołujący/wywoływany** widok ma trzy oddzielne części:  
  
    -   **Funkcje, które wywołały**: wszystkie funkcje, które wywołuje określoną funkcję znajduje się w górnej części widoku.  
  
    -   **Bieżąca funkcja**: konkretną funkcję, która została wywołana znajduje się w środkowej części widoku.  
  
    -   **Funkcje, które zostały wywołane przez** : wszystkie funkcje, które zostały wywołane przez konkretną funkcję znajduje się w dolnej części widoku.  
  
3.  Jeśli funkcja o nazwie `SyncToNavigator` pojawia się w środkowej części widoku, funkcje, które wywoływały `SyncToNavigator` funkcji są wyświetlane w górnej części widoku, a wszystkie funkcje, które zostały wywołane przez `SyncToNavigator` są wyświetlane w dolnej części widoku.  
  
4.  Funkcja w środkowej części widoku można zmienić, klikając dwukrotnie dowolny z wymienionych w dwóch częściach widoku funkcji. Widok jest następnie aktualizowany automatycznie zgodnie ze zmianami.  
  
5.  Można również sortować dane, klikając nazw kolumn.  
  
### <a name="select-calltree-view"></a>Wybierz widok alokowania  
  
1.  Wybierz **widok drzewa wywołań** w **bieżący widok** listy rozwijanej. Ten widok jest widok drzewa wykonywania programu.  
  
2.  **Widok drzewa wywołań** pokazuje drzewa jako nazwę procesu. Funkcje są węzły drzewa. Ten widok umożliwia przejście do śledzenia wywołań i analizować śledzenia, które mają największy wpływ na wydajność. Widok przypomina **widoku stosu wywołań** dostępne podczas debugowania. Oprócz kolumn w **widoku funkcji**w **widok drzewa wywołań**, ma dodatkową kolumnę do wyświetlenia **Nazwa modułu**.  
  
3.  Wybierz **znaczniki** w **bieżący widok** listy rozwijanej.  
  
4.  Profiler SLT istnieją znaczniki, które pojawiają się w strumieniu zbierania danych z komentarzem skojarzone. Znaczniki są miejsca w kodzie, które mają liczników. W przypadku Poinformuj Profiler XSLT można zebrać liczników wydajności XSLT liczniki Pobierz zbierane za każdym razem, gdy jeden z tych znaków pobiera wykonywane. Dane są wyświetlane w tabeli zawierające **Identyfikator znacznika**, **Nazwa znacznika** (**Uruchom Program**, **Program zakończenia**), a  **Sygnatury czasu**. Znaki nie są agregowane i wyświetlane w kolejności chronologicznej w **widoku znaczniki** raportu wydajności.  
  
### <a name="select-modules-in-the-current-view"></a>Wybierz moduł w bieżącym widoku  
  
1.  Wybierz **modułów** w **bieżący widok** listy rozwijanej.  
  
2.  Widok modułów jest płaską listę wszystkich funkcji agregowane na poziomie modułu. Rozwiń lub Zwiń Nazwa modułu do wyświetlania lub zamknąć widok danych dotyczących wydajności modułu. Dane można sortować, klikając nazwę kolumny. Domyślnie istnieją zarówno wartości bezwzględne, jak i numery procent **upłynęło całkowity czas**, **, który upłynął czas wyłączny**, **całkowity czas aplikacji**, **Własny czas aplikacji**, i **liczbę wywołań**.  
  
3.  Wybierz **procesu** w **bieżący widok** listy rozwijanej.  
  
4.  Widok procesu przedstawia tabelę, która zawiera **identyfikator procesu**, **nazwy procesu**, **czas rozpoczęcia**i **czas zakończenia**. Dane można sortować, klikając nazw kolumn.  
  
## <a name="see-also"></a>Zobacz też  
 [Przewodnik: Korzystanie z hierarchii XSLT](../xml-tools/walkthrough-using-xslt-hierarchy.md)



