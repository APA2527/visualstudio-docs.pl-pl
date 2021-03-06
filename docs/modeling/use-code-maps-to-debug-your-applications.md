---
title: Używanie map kodu do debugowania aplikacji
description: Dowiedz się, jak używać map kodu, aby uniknąć utraty w dużych bazach kodu, nieznanego kodu lub starszego kodu.
ms.custom: SEO-VS-2020
ms.date: 09/28/2018
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, visualizing code
- Visual Studio Ultimate, navigating code visually
- Visual Studio Ultimate, understanding code
- Visual Studio Ultimate, mapping code relationships
- Visual Studio Ultimate, code maps
- mapping code relationships
- code maps
- mapping relationships in code
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: a39be2e465ebe8b04501f319e89d6f8bc926b4c2
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99924466"
---
# <a name="use-code-maps-to-debug-your-applications"></a>Używanie map kodu do debugowania aplikacji

Mapy kodu mogą pomóc uniknąć utraty w dużych bazach kodu, nieznanego kodu lub starszego kodu. Na przykład podczas debugowania, może być konieczne odnalezienie kodu w wielu plikach i projektach. Za pomocą map kodu można nawigować po fragmentach kodu i zrozumieć relacje między nimi. Dzięki temu nie trzeba śledzić tego kodu w Twoim nagłówku ani rysować oddzielnego diagramu. Dlatego w przypadku przerwania pracy mapy kodu ułatwiają odświeżenie pamięci o kodzie, nad którym pracujesz.

![Mapa kodu &#45; relacje mapy w kodzie](../modeling/media/codemapstoryboardpaint.png)

**Zielona strzałka pokazuje, gdzie znajduje się kursor w edytorze**

Aby uzyskać szczegółowe informacje o poleceniach i akcjach, których można używać podczas pracy z mapami kodu, zobacz [przeglądanie i zmiana rozmieszczenia map kodu](../modeling/browse-and-rearrange-code-maps.md).

> [!NOTE]
> Do tworzenia i edytowania map kodu potrzebna jest wersja Visual Studio Enterprise. W programie Visual Studio Community i wersje Professional można otwierać diagramy, które zostały wygenerowane w wersji Enterprise, ale nie można ich edytować.

## <a name="understand-the-problem"></a>Omówienie problemu
 Przypuśćmy, że w programie graficznym, nad którym pracujesz, znajduje się błąd. Aby odtworzyć usterkę, należy otworzyć rozwiązanie w programie Visual Studio i nacisnąć klawisz **F5** , aby rozpocząć debugowanie.

 Po narysowaniu linii i wybraniu **polecenia Cofnij moje ostatnie pociągnięcie** nic się nie dzieje, aż do rysowania następnego wiersza.

 ![&#45; błędów Odtwórz mapy kodu](../modeling/media/codemapstoryboardpaint0.png)

 Aby rozpocząć badanie, Wyszukaj `Undo` metodę. Znajdziesz go w `PaintCanvas` klasie.

 ![Mapa kodu &#45; Znajdź kod](../modeling/media/codemapstoryboardpaint1.png)

## <a name="start-mapping-the-code"></a>Uruchamianie mapowania kodu
 Teraz Rozpocznij mapowanie `undo` metody i jej relacji. W edytorze kodu należy dodać `undo` metodę i pola, do których się odwołuje, do nowej mapy kodu. Podczas tworzenia nowej mapy może trochę czasu może zająć indeksowanie kodu. Dzięki temu następne operacje działają szybciej.

 ![Mapa kodu &#45; Pokaż metodę i powiązane pola](../modeling/media/codemapstoryboardpaint3.png)

> [!TIP]
> Zielone podświetlenie pokazuje ostatnie elementy dodane do mapy. Zielona strzałka pokazuje pozycję kursora w kodzie. Strzałki między elementami reprezentują różne relacje. Aby uzyskać więcej informacji na temat elementów na mapie, przesuń wskaźnik myszy nad nich i zbadaj ich etykietki narzędzi.

 ![Mapa kodu &#45; Pokaż etykietki narzędzi](../modeling/media/codemapstoryboardpaint4.png)

## <a name="navigate-and-examine-code-from-the-map"></a>Nawigowanie i sprawdzanie kodu z mapy
 Aby zobaczyć definicję kodu dla każdego pola, kliknij dwukrotnie pole na mapie lub zaznacz pole i naciśnij klawisz **F12**. Zielona strzałka przesuwa się między elementami na mapie. Kursor w edytorze kodu również przesuwa się automatycznie.

 ![Zrzut ekranu okna mapy kodu z wybranym polem historii i oknem edytora kodu, w którym są wyróżnione wszystkie wystąpienia historii.](../modeling/media/codemapstoryboardpaint5.png)

 ![Zrzut ekranu okna mapy kodu z wybranym polem paintObjects oraz oknem edytora kodu, w którym są wyróżnione wszystkie wystąpienia elementu paintObjects.](../modeling/media/codemapstoryboardpaint5a.png)

> [!TIP]
> Zieloną strzałkę na mapie możesz również przesunąć, przesuwając kursor w edytorze kodu.

## <a name="understand-relationships-between-pieces-of-code"></a>Omówienie relacji między fragmentami kodu
 Teraz chcesz wiedzieć, który inny kod współdziała z `history` `paintObjects` polami i. Możesz dodać do mapy wszystkie metody odwołujące się do tych pól. Można to zrobić z poziomu mapy lub z edytora kodu.

 ![Mapa kodu &#45; Znajdź wszystkie odwołania](../modeling/media/codemapstoryboardpaint6.png)

 ![Otwieranie mapy kodu z poziomu edytora kodu](../modeling/media/codemapstoryboardpaint6a.png)

> [!NOTE]
> Jeśli dodasz elementy z projektu, który jest współużytkowany przez wiele aplikacji, takich jak Windows Phone lub Sklep Windows, wówczas te elementy zawsze pojawiają się z aktualnie aktywnym projektem aplikacji na mapie. Dlatego jeśli zmienisz kontekst na inny projekt aplikacji, kontekst na mapie również zmieni się dla wszystkich nowo dodanych elementów z projektu udostępnionego. Operacje wykonywane za pomocą elementu na mapie dotyczą tylko tych elementów, które współużytkują ten sam kontekst.

 Zmień układ, aby przeorganizować przepływ relacji i poprawić czytelność mapy. Elementy na mapie możesz również przesuwać, przeciągając je.

 ![Zrzut ekranu okna mapy kodu z otwartym menu Układ i poleceniem Left to Rgiht.](../modeling/media/codemapstoryboardpaint7a.png)

> [!TIP]
> Domyślnie opcja **Układ przyrostowy** jest włączona. Dzięki temu mapa jest reorganizowana w możliwie najmniejszym stopniu przy dodawaniu nowych elementów. Aby ponownie rozmieścić całą mapę przy każdym dodawaniu nowych elementów, wyłącz opcję **Układ przyrostowy**.

 ![Zrzut ekranu przedstawiający okno mapy kodu z strzałkami relationshiop między polami wskazującymi od lewej do prawej.](../modeling/media/codemapstoryboardpaint7.png)

 Zbadajmy te metody. Na mapie kliknij dwukrotnie metodę **metodę PaintCanvas** lub wybierz tę metodę i naciśnij klawisz **F12**. Dowiesz się, że ta metoda tworzy `history` i `paintObjects` jako puste listy.

 ![Zrzut ekranu okna mapy kodu z wybraną metodą metodę PaintCanvas i obrazem fragmentu kodu pokazującym wyróżnioną nazwę metody PainCanvas.](../modeling/media/codemapstoryboardpaint8.png)

 Teraz Powtórz te same kroki, aby przeanalizować `clear` definicję metody. Nauczysz się, że program `clear` wykonuje pewne zadania z `paintObjects` i `history` . Następnie wywołuje `Repaint` metodę.

 ![Zrzut ekranu okna mapy kodu z wybraną metodą Clear i obrazem fragmentu kodu pokazującym kod metody Clear.](../modeling/media/codemapstoryboardpaint9.png)

 Teraz sprawdź `addPaintObject` definicję metody. Wykonuje również pewne zadania z `history` i `paintObjects` . Również wywołuje `Repaint` .

 ![Zrzut ekranu okna mapy kodu z wybraną metodą addPaintObject i obrazem fragmentu kodu pokazującym kod dla metody addPaintObject.](../modeling/media/codemapstoryboardpaint10.png)

## <a name="find-the-problem-by-examining-the-map"></a>Znajdowanie problemu poprzez analizowanie mapy
 Wydaje się, że wszystkie metody, które modyfikują `history` i `paintObjects` wywołują `Repaint` . `undo`Metoda nie jest jeszcze wywoływana `Repaint` , mimo że `undo` modyfikuje te same pola. Dlatego możesz rozwiązać ten problem, wywołując `Repaint` od `undo` .

 ![Mapa kodu &#45; Znajdź brakujące wywołanie metody](../modeling/media/codemapstoryboardpaint11.png)

 Nie mając mapy, z której wynika, że brak tego wywołania, znalezienie problemu mogłoby być trudniejszy, zwłaszcza przy bardziej skomplikowanym kodzie.

## <a name="share-your-discovery-and-next-steps"></a>Przekazanie ustaleń innym osobom i następne kroki
 Zanim Ty lub ktokolwiek inny rozwiąże ten problem, można robić na mapie notatki dotyczące problemu i sposobach jego rozwiązania.

 ![Mapa kodu &#45; komentarz i flaguje elementy do powstawania](../modeling/media/codemapstoryboardpaint12.png)

 Na przykład możesz dodać komentarze do mapy i flagować elementy przy użyciu kolorów.

 ![Mapa kodu &#45; z komentarzem i oflagowanymi elementami](../modeling/media/codemapstoryboardpaint12a.png)

 Jeśli masz zainstalowany program Microsoft Outlook, możesz wysłać mapę do innych osób pocztą e-mail. Mapę możesz również wyeksportować jako obraz lub w innym formacie.

 ![Mapa kodu &#45; udział, eksport, poczta](../modeling/media/codemapstoryboardpaint13.png)

## <a name="fix-the-problem-and-show-what-you-did"></a>Rozwiązanie problemu i pokazanie innym, co zostało zrobione
 Aby naprawić ten błąd, należy dodać wywołanie `Repaint` do `undo` .

 ![&#45; dodać brakującego wywołania metody w mapie kodu](../modeling/media/codemapstoryboardpaint14.png)

 Aby potwierdzić rozwiązanie problemu, ponownie uruchom sesję debugowania i spróbuj odtworzyć błąd. Teraz wybranie opcji **Cofnij ostatnie pociągnięcie** działa zgodnie z oczekiwaniami i potwierdza, że wprowadzono poprawną poprawkę.

 ![Mapa kodu &#45; Potwierdź poprawkę kodu](../modeling/media/codemapstoryboardpaint15.png)

 Możesz zaktualizować mapę, aby pokazać wprowadzoną poprawkę.

 ![Mapa kodu &#45; aktualizacji mapy z brakującym wywołaniem metody](../modeling/media/codemapstoryboardpaint16.png)

 Mapa zawiera teraz link między **poleceniami Cofnij** i **odświeżenia**.

 ![Mapa kodu &#45; zaktualizowana mapa z wywołaniem metody](../modeling/media/codemapstoryboardpaint17.png)

> [!NOTE]
> Po zaktualizowaniu mapy, może pojawić się komunikat o zaktualizowaniu indeksu kodu użytego do utworzenia mapy. Oznacza to, że ktoś zmienił kod, co powoduje, że mapa nie pasuje do bieżącego kodu. Nie zatrzymuje to aktualizowania mapy, ale może być konieczne ponowne utworzenie mapy w celu potwierdzenia, że pasuje do kodu.

 Teraz dowiesz się, jak to zrobić. Problem został znaleziony i rozwiązany pomyślnie dzięki mapowaniu kodu. Istnieje również mapa pomagająca w nawigowaniu po kodzie, zapamiętaniu nowych informacji, a także pokazująca kroki, które zostały podjęte w celu rozwiązania problemu.

## <a name="see-also"></a>Zobacz też

- [Metody mapowania dla stosu wywołań podczas debugowania](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
- [Tworzenie wizualizacji kodu](../modeling/visualize-code.md)
