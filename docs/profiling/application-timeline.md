---
title: Analizowanie zużycia zasobów w aplikacjach XAML w programie Visual Studio | Dokumentacja firmy Microsoft
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: df7d854b-0a28-45a9-8a64-c015a4327701
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: f297b9202dabfcfe40ea63b187bc914e187b974f
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2018
ms.locfileid: "42623897"
---
# <a name="analyze-resource-consumption-and-ui-thread-activity-xaml"></a>Analizowanie zużycia zasobów i aktywności wątku interfejsu użytkownika (XAML)
Użyj **oś czasu aplikacji** profiler, aby znaleźć i naprawić interakcji aplikacji dotyczące problemów z wydajnością w aplikacjach XAML. To narzędzie pomaga w zwiększeniu wydajności aplikacji XAML, zapewniając szczegółowy widok wykorzystania zasobów aplikacji. Możesz analizować czas spędzony przez aplikację na przygotowanie ramek interfejsu użytkownika (układ i renderowania), obsługi żądań dysku i sieci oraz w scenariuszach, takich jak uruchamianie aplikacji i ładowanie strony i rozmiar Windows.  
  
 **Oś czasu aplikacji** jest jednym z narzędzi, można uruchomić z **debugowania** > **Profiler wydajności** polecenia.  
  
 To narzędzie zastępuje **XAML UI Responsiveness** narzędzie, które było częścią zestawu narzędzi diagnostycznych dla programu Visual Studio 2013.  
  
 To narzędzie służy na następujących platformach:  
  
1.  Windows Universal apps (w systemie Windows 10)  
  
2.  Windows 8.1  
  
4.  Windows Presentation Foundation (.Net 4.0 i nowsze)  
  
5.  Windows 7  
  
> [!NOTE]
>  Można zbierać i analizować dane użycia procesora CPU i dane zużycia energii, wraz z **ApplicationTimeline** danych. Zobacz [uruchamianie narzędzi z lub bez debugera profilowania](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
## <a name="collect-application-timeline-data"></a>Zbieranie danych oś czasu aplikacji  
 Czas reakcji aplikacji można profilować na komputerze lokalnym, podłączone urządzenie, symulatorze programu Visual Studio lub emulatorach lub urządzenie zdalne. Zobacz [uruchamianie narzędzi z lub bez debugera profilowania](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
> [!TIP]
>  Jeśli to możliwe Uruchom aplikację bezpośrednio na urządzeniu. Wydajność aplikacji obserwowana na symulatorze lub za pośrednictwem połączenia pulpitu zdalnego może nie być taka sama jak rzeczywista wydajność na urządzeniu. Z drugiej strony zbieranie danych przy użyciu narzędzia zdalne programu Visual Studio nie wpływa na dane wydajności.  
  
 Poniżej przedstawiono podstawowe kroki:  
  
1.  Otwórz aplikację XAML.  
  
2.  Kliknij przycisk **debugowanie / Profiler wydajności**. Powinien zostać wyświetlony listę narzędzi w oknie .diagsession profilowania.  
  
3.  Wybierz **oś czasu aplikacji** a następnie kliknij przycisk **Start** w dolnej części okna.  
  
    > [!NOTE]
    >  Może widzieć okno Kontrola konta użytkownika żądaniem udzielenia uprawnienia do uruchamiania *VsEtwCollector.exe*. Kliknij przycisk **Tak**.  
  
4.  Uruchom scenariuszu jesteś zainteresowany profilowania w aplikacji, aby zbierać dane dotyczące wydajności.  
  
5.  Aby zatrzymać profilowanie, Przełącz do okna .diagsession, a następnie kliknij przycisk **zatrzymać** w górnej części okna.  
  
     Program Visual Studio analizuje zebrane dane i wyświetla wyniki.  
  
     ![Raport programu profilującego osi czasu](../profiling/media/timeline_base.png "TIMELINE_Base")  
  
## <a name="analyze-timeline-profiling-data"></a>Analizowanie danych profilowania osi czasu  
 Po zebraniu danych profilowania można wykonać poniższe kroki, aby rozpocząć analizę:  
  
1.  Zapoznaj się z informacjami w **wykorzystanie wątku interfejsu użytkownika** i **przepustowość wizualna (kl. / s)** wykresów, a następnie użyj pasków nawigacyjnych osi czasu, aby wybrać zakres czasu do przeanalizowania.  
  
2.  Korzystając z informacji podanych w **wykorzystanie wątku interfejsu użytkownika** lub **przepustowość wizualna (kl. / s)** wykresy, sprawdź szczegóły w **szczegóły osi czasu** widok, aby wykryć możliwe przyczyny Aby uzyskać widocznego wydłużenia czasu odpowiedzi.  
  
###  <a name="BKMK_Report_scenarios_categories_and_events"></a> Scenariusze, kategorii lub zdarzeń  
 **Oś czasu aplikacji** narzędzie wyświetli dane chronometrażu dla scenariuszy, kategorie i zdarzenia, które są związane z wydajnością XAML.  
  
###  <a name="BKMK_Diagnostic_session_timeline"></a> Oś czasu sesji diagnostycznej  
 ![Oś czasu wydajności i diagnostyki](../profiling/media/diaghub_timelinewithusermarks.png "DIAGHUB_TimelineWithUserMarks")  
  
 Linijka u góry strony pokazuje oś czasu dla profilowanych informacji. Ta oś czasu ma zastosowanie do obu **wykorzystanie wątku interfejsu użytkownika** wykresu i **przepustowość wizualna** wykresu. Można zawęzić zakres raportu, przeciągając paski nawigacyjne na osi czasu w celu zaznaczenia segmentu osi czasu.  
  
 Na osi czasu są także wyświetlane wstawione znaczniki użytkownika oraz zdarzenia cyklu życia aktywacji aplikacji.  
  
###  <a name="BKMK_UI_thread_utilization_graph"></a> Wykres wykorzystania wątku interfejsu użytkownika  
 ![Wykres wykorzystania procesora CPU](../profiling/media/timeline_cpuutilization.png "TIMELINE_CpuUtilization")  
  
 **Wykorzystanie wątku interfejsu użytkownika (%)** wykresu jest wykres słupkowy, który wyświetla względna ilość czasu spędzonego w kategorii, aby w przedziale kolekcji.  
  
###  <a name="BKMK_Visual_throughput_FPS_graph"></a> Wykres przepustowość wizualna (kl. / s)  
 ![Wykres przepustowość wizualna](../profiling/media/timeline_visualthroughput.png "TIMELINE_VisualThroughput")  
  
 **Przepustowość wizualna (kl. / s)** wykres liniowy pokazuje liczbę klatek na sekundę (kl. / s) w wątku interfejsu użytkownika i kompozycję aplikacji.  
  
###  <a name="BKMK_Timeline_details_"></a> Szczegóły osi czasu  
 Widok szczegółów jest, gdzie będą spędzać większość czasu analizowanie raportu. Pokazuje szczegółowy widok wykorzystania procesora CPU pogrupowane według podsystemu struktury interfejsu użytkownika lub składnik systemu, który procesor CPU wykorzystany aplikacji.  
  
 Obsługiwane są następujące zdarzenia:  
  
|||  
|-|-|  
|**Analiza kodu**|Czas poświęcony na podczas analizowania plików XAML i tworzenia obiektów.<br /><br /> Rozwijanie **analizowanie** w węźle **szczegóły osi czasu** Wyświetla łańcuch zależności, wszystkie pliki XAML, które były analizowane w wyniku zdarzenia katalogu głównego. Umożliwi to można zidentyfikować niepotrzebnego pliku podczas analizowania i obiektu tworzenia w scenariuszach poufnych wydajności i zoptymalizować je automatycznie.|  
|**Układ**|W przypadku dużych aplikacji tysięcy elementów mogą być wyświetlane na ekranie, w tym samym czasie. Może to spowodować niska szybkość klatek interfejsu użytkownika i czas odpowiedzi aplikacji odpowiednio niska. Zdarzenie układu określają dokładnie koszt układania każdego elementu (oznacza to, że czas spędzony w rozmieszczanie, miary, ApplyTemplate, ArrangeOverride i MeasureOverride) i tworzy drzew wizualne, które uczestniczyła w przekazanie układu. Aby określić, które drzewa logiczne Oczyść lub oceny innych mechanizmów opóźnienia, aby zoptymalizować układ subskrypcji — okres próbny, można użyć tej wizualizacji.|  
|**Renderowanie**|Czas poświęcony na rysunku elementów XAML do ekranu.|  
|**I/0**|Czas poświęcony na pobieranie danych z dysku lokalnego lub z zasobów sieciowych, które są dostępne za pośrednictwem [Microsoft Windows Internet (WinINet) interfejsu API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa385331.aspx).|  
|**Kod aplikacji**|Czas poświęcony na wykonywanie kodu aplikacji (użytkownik), który nie jest związany z analizą składni ani układu.|  
|**XAML — inne**|Czas poświęcony na wykonywanie kodu czasu wykonywania XAML.|  
  
> [!TIP]
>  Wybierz **użycie procesora CPU** narzędzia wraz z **oś czasu aplikacji** narzędzia w przypadku uruchamiania profilowania na przeglądanie aplikacji metod, które są wykonywane w wątku interfejsu użytkownika. Przenoszenie kodu aplikacji długotrwałych do wątku w tle może poprawić czas odpowiedzi interfejsu użytkownika.  
  
####  <a name="BKMK_Customizing_Timeline_details_"></a> Dostosowywanie szczegóły osi czasu  
 Użyj **szczegóły osi czasu** narzędzi, aby sortowanie, filtrowanie i podaj adnotacje **szczegóły osi czasu** zapisy.  
  
|||  
|-|-|  
|**Sortuj według**|Sortuj według czasu rozpoczęcia lub długość zdarzenia.|  
|![Grupuj zdarzenia według ramki](../profiling/media/timeline_groupbyframes.png "TIMELINE_GroupByFrames")|Dodaje lub usuwa najwyższego poziomu **ramki** kategorię, która grupuje zdarzenia przez ramkę.|  
|![Lista szczegółów osi czasu filtrów](../profiling/media/timeline_filter.png "TIMELINE_Filter")|Filtruje listę według wybranych kategorii i długość zdarzenia.|  
|![Dostosowywanie osi czasu szczegółowe informacje o](../profiling/media/timeline_viewsettings.png "TIMELINE_ViewSettings")|Umożliwia określenie adnotacje do zdarzenia.|  
  
## <a name="see-also"></a>Zobacz także  
 [Blog zespołu programu WPF: nowy interfejs użytkownika narzędzia do analizy wydajności dla aplikacji WPF](http://blogs.msdn.com/b/wpf/archive/2015/01/16/new-ui-performance-analysis-tool-for-wpf-applications.aspx)  
 [Wydajność — najlepsze rozwiązania dla aplikacji platformy uniwersalnej systemu Windows przy użyciu języka C++, C# i Visual Basic](http://msdn.microsoft.com/en-us/567bcefa-5da5-4e42-a4b8-1358c71adfa2)   
 [Optymalizowanie wydajności aplikacji WPF](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)  
 [Profilowanie w programie Visual Studio](../profiling/index.md)  
 [Pierwsze spojrzenie na narzędziach profilowania](../profiling/profiling-feature-tour.md)
