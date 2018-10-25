---
title: Analizowanie użycia procesora CPU w programie Visual Studio | Dokumentacja firmy Microsoft
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7501a20d-04a1-480f-a69c-201524aa709d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f63e4f43db3f8c4b24b43bda02cf00b52befc94
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49842186"
---
# <a name="analyze-cpu-usage"></a>Analizowanie użycia procesora CPU
Jeśli musisz zbadać problemy z wydajnością w aplikacji, dobrym miejscem do rozpoczęcia jest zrozumienie, sposobem użycia procesora CPU. **Użycie procesora CPU** narzędzie pokazuje, gdzie Procesor spędza czasu wykonywania Visual C++, Visual C# / Visual Basic oraz kodu JavaScript. Począwszy od programu Visual Studio 2015 Update 1, możesz zobaczyć podział użycia procesora CPU dla poszczególnych funkcji bez opuszczania debugera. Włącz profilowanie procesora CPU włączać i wyłączać podczas debugowania i wyświetlania wyników, gdy wykonanie zostanie zatrzymana, na przykład w punkcie przerwania.  
  
Masz kilka opcji uruchamiania i zarządzania nimi sesję diagnostyczną. Na przykład, można uruchomić **użycie procesora CPU** narzędzia na maszynach lokalnych lub zdalnych lub na w symulatorze lub w emulatorze. Można analizować wydajność Otwórz projekt w programie Visual Studio dołączony do uruchomionej aplikacji, lub uruchomić aplikację, która jest instalowana z Microsoft Store. Aby uzyskać więcej informacji, zobacz [uruchamianie narzędzi profilowania z debugerem lub bez debugera](../profiling/running-profiling-tools-with-or-without-the-debugger.md). 

W tym miejscu pokazujemy, jak zbierać i analizować użycie procesora CPU z kompilacjami wydania. Aby Analizowanie użycia procesora CPU podczas debugowania, zobacz [profilowanie wydajności — przewodnik dla początkujących](../profiling/beginners-guide-to-performance-profiling.md).

Windows 7 lub nowszy jest wymagany do korzystania z narzędzia profilowania, przedstawione w tym artykule, czyli [Profiler wydajności](../profiling/profiling-feature-tour.md).
  
##  <a name="collect-cpu-usage-data"></a>Zbieranie danych użycia procesora CPU  
  
1. W programie Visual Studio, należy ustawić Konfiguracja rozwiązania **wersji** i wybierz cel wdrożenia.  
  
    ![Wybieranie wersji i komputer lokalny](../profiling/media/cpuuse_selectreleaselocalmachine.png "CPUUSE_SelectReleaseLocalMachine")  
  
   -   Aplikacja uruchomiona w **wersji** tryb zapewnia lepsze widok rzeczywistej wydajności aplikacji.  
  
   -   Uruchamianie aplikacji na komputerze lokalnym, najlepiej replikuje wykonywanie zainstalowanych aplikacji.  
  
   -   Jeśli dane są zbierane z urządzeniem zdalnym, uruchom aplikację bezpośrednio na urządzeniu, a nie za pomocą połączenia pulpitu zdalnego.  
  
   -   W przypadku aplikacji Windows Phone, zbieranie danych bezpośrednio z **urządzenia** zapewnia najbardziej dokładnych danych.  
  
2. Na **debugowania** menu, wybierz **Profiler wydajności**.  
  
3. Wybierz **użycie procesora CPU** , a następnie wybierz **Start**.  
  
    ![Wybierz opcję użycia procesora CPU](../profiling/media/cpuuse_lib_choosecpuusage.png "CPUUSE_LIB_ChooseCpuUsage")  
  
4. Po uruchomieniu aplikacji, kliknij przycisk **uzyskać maksymalna liczba**. Poczekaj około sekundy po wyświetleniu danych wyjściowych, a następnie wybierz **uzyskać maksymalny numer Async**. Oczekiwania między kliknięć przycisków sprawia, że ułatwiają izolowanie przycisk kliknij procedur w raport diagnostyczny.  
  
5. Gdy zostanie wyświetlony drugi wiersz danych wyjściowych, wybierz **Zatrzymaj Kolekcjonowanie** w Centrum wydajności i diagnostyki.  
  
   ![Zatrzymaj zbieranie danych CpuUsage](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
   Narzędzie użycie procesora CPU analizuje dane i wyświetla raport.  
  
   ![Raport CpuUsage](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
## <a name="analyze-the-cpu-usage-report"></a>Analizowanie raportu użycia procesora CPU  
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a> Użycie procesora CPU drzewo wywołań  
 Aby rozpocząć pracę, informacje o informacje na temat drzewa wywołań, wybierz ponownie `GetMaxNumberButton_Click` segmentu i spójrz na szczegóły drzewa wywołań.  
  
####  <a name="BKMK_Call_tree_structure"></a> Struktura drzewa wywołań  
 ![GetMaxNumberButton&#95;kliknij wywołanie drzewa](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "CPU_USE_WT_GetMaxNumberCallTree_annotated")  
  
|||  
|-|-|  
|![Krok 1](../profiling/media/procguid_1.png "ProcGuid_1")|Węzeł najwyższego poziomu w drzewach wywołanie użycie procesora CPU jest pseudo-węzłem|  
|![Krok 2](../profiling/media/procguid_2.png "ProcGuid_2")|W przypadku większości aplikacji gdy **Pokaż kod zewnętrzny** opcja jest wyłączona, węzeł drugiego poziomu, który jest **[kod zewnętrzny]** węzeł zawierający system i platforma kod, który uruchamia i zatrzymuje aplikację, rysuje interfejsu użytkownika kontroluje planowanie wątków i zapewnia inne niskopoziomowe usługi dla aplikacji.|  
|![Krok 3](../profiling/media/procguid_3.png "ProcGuid_3")|Elementy podrzędne węzła drugiego poziomu są asynchroniczne procedur, które są nazywane lub utworzonych przez system drugiego poziomu oraz kodu struktury i metody kod użytkownika.|  
|![Krok 4](../profiling/media/procguid_4.png "ProcGuid_4")|Węzły podrzędne metody zawierają dane tylko w przypadku wywołania metody nadrzędnej. Gdy **Pokaż kod zewnętrzny** jest wyłączona, metody aplikacja może również zawierać **[kod zewnętrzny]** węzła.|  
  
####  <a name="BKMK_External_Code"></a> Kod zewnętrzny  
 Kod zewnętrzny są funkcje w system i platforma składników, które są wykonywane przez tworzonego kodu. Kod zewnętrzny obejmują funkcje, które Uruchom i Zatrzymaj aplikację, narysuj interfejsu użytkownika, kontrolować wątki i podaj inne niskopoziomowe usługi dla aplikacji. W większości przypadków nie będzie zainteresowani kod zewnętrzny, a więc użycie procesora CPU wywołać drzewa zbiera informacje funkcji zewnętrznych metody użytkownika w jednym **[kod zewnętrzny]** węzła.  
  
 Gdy chcesz wyświetlić ścieżki wywołanie kodu zewnętrznego, wybierz pozycję **Pokaż kod zewnętrzny** z **filtrowania widoku** listy, a następnie wybierz **Zastosuj**.  
  
 ![Wybierz Widok filtrów, a następnie Pokaż kod zewnętrzny](../profiling/media/cpu_use_wt_filterview.png "CPU_USE_WT_FilterView")  
  
 Należy pamiętać, że wiele łańcuchy wywołania kodu zewnętrznego głęboko zagnieżdżone, tak, aby szerokość kolumny nazwy funkcji może być dłuższa niż szerokość wyświetlanie wszystkich pól poza największych monitorów komputera. W takim wypadku nazwy funkcji są wyświetlane jako **[...]** :  
  
 ![Zagnieżdżony kod zewnętrzny, w drzewie wywołań](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "CPU_USE_WT_ShowExternalCodeTooWide")  
  
 Użyj pola wyszukiwania, aby odnaleźć węzła, którego szukasz, a następnie użyj poziomych pasków przewijania do przenoszenia danych do wyświetlenia:  
  
 ![Wyszukaj zagnieżdżonego kodu zewnętrznego](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "CPU_USE_WT_ShowExternalCodeTooWide_Found")  
  
###  <a name="BKMK_Call_tree_data_columns"></a> Kolumny danych drzewo wywołań  
  
|||  
|-|-|  
|**Łączny czas Procesora (%)**|![Łączna liczba % danych równania](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> Procent aktywności procesora CPU przez aplikację w wybranym zakresie czasu użytego przez wywołania funkcji i funkcji wywoływanych przez funkcję. Należy pamiętać, że to różni się od **wykorzystanie procesora CPU** wykres osi czasu, który porównuje łączną aktywność aplikacji w zakres czasu, aby całkowita dostępna pojemność procesora CPU.|  
|**Własny Procesora (%)**|![Równania własnym %](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> Procent aktywności procesora CPU przez aplikację w wybranym zakresie czasu użytego przez wywołanie funkcji, z wyłączeniem aktywności funkcji wywołanych przez funkcję.|  
|**Łączny czas Procesora (ms)**|Liczba milisekund spędzonych wykonywaniu w wywołaniach funkcji w wybranym zakresie czasu i funkcje, które zostały wywołane przez funkcję.|  
|**Własny procesora CPU (ms)**|Liczba milisekund spędzonych wykonywaniu w wywołaniach funkcji w wybranym zakresie czasu i funkcje, które zostały wywołane przez funkcję, z wyłączeniem aktywności funkcji wywołanych przez funkcję.|  
|**Module**|Nazwa modułu zawierającego funkcję lub liczba modułów zawierających funkcje w węźle [kod zewnętrzny].|  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a> Funkcje asynchroniczne użycia procesora CPU w drzewie wywołań  
 Gdy kompilator napotka metody asynchronicznej, tworzy ukrytej klasy, aby kontrolować wykonywanie metody. Koncepcyjnie klasa jest automatu stanów, zawierający listę generowanych przez kompilator funkcje asynchroniczne, wywoływanie operacji oryginalnej metody i wywołania zwrotne, harmonogram i Iteratory wymagane do wykonania ich poprawnie. Oryginalnej metody wywołanego przez nadrzędne metodę środowiska uruchomieniowego usuwa metodę z kontekstu wykonania elementu nadrzędnego, a następnie uruchamia metody klasy ukryte w kontekście systemu i struktury kodu, który kontrolować wykonywanie aplikacji. Metody asynchroniczne są często, ale nie zawsze wykonywane w różnych wątkach co najmniej jeden. Ten kod jest wyświetlany w drzewie wywołań użycie procesora CPU jako elementy podrzędne **[kod zewnętrzny]** węzeł bezpośrednio pod górny węzeł drzewa.  
  
 Aby to zobaczyć, w tym przykładzie, wybierz ponownie `GetMaxNumberAsyncButton_Click` segment na osi czasu.  
  
 ![GetMaxNumberAsyncButton&#95;kliknij element raportu](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 Pierwsze dwa węzły w obszarze **[kod zewnętrzny]** są generowane przez kompilator metody klasy maszyny stanu. Trzeci to wywołanie do oryginalnej metody. Rozwijanie wygenerowane metody dowiesz się, co się dzieje.  
  
 ![Rozwinięte GetMaxNumberAsyncButton&#95;kliknij wywołanie drzewa](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click` bardzo niewiele; jego zarządza listą wartości zadania, oblicza maksymalną liczbę wyników i wyświetla dane wyjściowe.  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext` Dowiesz się, działania wymagane do planowania i uruchamiania zadań 48, które opakować wywołanie `GetNumberAsync`.  
  
-   `MainPage::<GetNumberAsync>b__b` Dowiesz się, aktywności zadań, które wywołują `GetNumber`.
