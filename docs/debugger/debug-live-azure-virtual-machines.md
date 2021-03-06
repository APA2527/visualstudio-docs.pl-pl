---
title: Debugowanie maszyn wirtualnych i zestawów skalowania na żywo usługi Live ASP.NET
description: Dowiedz się, w jaki sposób używać Snapshot Debugger w programie Visual Studio, aby ustawiać punkty przyciągania i wykonywać migawki podczas debugowania aplikacji Live ASP.NET na maszynach wirtualnych i zestawach skalowania platformy Azure.
ms.custom: SEO-VS-2020
ms.date: 02/06/2019
ms.topic: how-to
helpviewer_keywords:
- debugger
author: poppastring
ms.author: madownie
manager: andster
monikerRange: '>= vs-2019'
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 9ed85616080859cd69c44c66b442f3f46d81f51a
ms.sourcegitcommit: d577818d3d8e365baa55c6108fa8159c46ed8b43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/01/2021
ms.locfileid: "97846952"
---
# <a name="debug-live-aspnet-apps-on-azure-virtual-machines-and-azure-virtual-machine-scale-sets-using-the-snapshot-debugger"></a>Debuguj aplikacje Live ASP.NET na maszynach wirtualnych platformy Azure i w zestawach skalowania maszyn wirtualnych platformy Azure przy użyciu Snapshot Debugger

Snapshot Debugger wykonuje migawkę aplikacji w środowisku produkcyjnym, gdy interesujący kod jest wykonywany. Aby polecić debugerowi wykonanie migawki, należy ustawić punkty przyciągania i punkty rejestrowania w kodzie. Debuger pozwala zobaczyć dokładnie, co poszło źle, bez wpływu na ruch aplikacji produkcyjnej. Snapshot Debugger może pomóc znacząco skrócić czas potrzebny do rozwiązania problemów występujących w środowiskach produkcyjnych.

Punkty przyciągania i punkty rejestrowania są podobne do punktów przerwania, ale w przeciwieństwie do punktów przerwania, punkty przyciągania nie wstrzymuje aplikacji po trafieniu. Zwykle przechwytywanie migawki w punkt przyciągania trwa 10-20 milisekund.

W tym samouczku wykonasz następujące czynności:

> [!div class="checklist"]
> * Uruchom Snapshot Debugger
> * Ustaw punkt przyciągania i Wyświetl migawkę
> * Ustaw punkt rejestrowania

## <a name="prerequisites"></a>Wymagania wstępne

* Snapshot Debugger dla Virtual Machines platformy Azure i Virtual Machine Scale Sets platformy Azure są dostępne tylko dla programu Visual Studio 2019 Enterprise lub nowszego z **obciążeniem programowania na platformie Azure**. (Na karcie **poszczególne składniki** znajdziesz ją w obszarze **debugowanie i testowanie**  >  **Debuger migawek**.)

    Jeśli nie jest jeszcze zainstalowana, zainstaluj [program Visual Studio 2019 Enterprise](https://visualstudio.microsoft.com/vs/).

* Kolekcja migawek jest dostępna dla następujących aplikacji sieci Web usługi Azure Virtual Machines\Virtual Machine Scale:
  * ASP.NET aplikacje działające w .NET Framework 4.6.1 lub nowszych.
  * ASP.NET Core aplikacje działające na platformie .NET Core 2,0 lub nowszej w systemie Windows.

  > [!NOTE]
  >  Visual Studio Enterprise uruchomiony w 32-bitowej wersji systemu Windows nie będzie mógł wyświetlać migawek.

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>Otwórz projekt i uruchom Snapshot Debugger

1. Otwórz projekt, dla którego chcesz debugować migawkę.

    > [!IMPORTANT]
    > Aby przeprowadzić debugowanie migawek, należy otworzyć tę *samą wersję kodu źródłowego* , która jest publikowana w usłudze Azure Virtual Machine\Virtual.

1. Wybierz **> debugowania Snapshot Debugger Dołącz...**. Wybierz zestaw skalowania maszyn wirtualnych platformy Azure, do którego wdrożono aplikację sieci Web, i konto usługi Azure Storage, a następnie kliknij przycisk **Dołącz**. Snapshot Debugger również obsługuje [usługę Azure Kubernetes](debug-live-azure-kubernetes.md) i [Azure App Service](debug-live-azure-applications.md).

    ![Uruchom Debuger migawek z menu Debuguj](../debugger/media/snapshot-debug-menu-attach.png)

    ![Wybierz zasób platformy Azure](../debugger/media/snapshot-select-azure-resource-vm.png)

    > [!IMPORTANT]
    > Po pierwszym wybraniu opcji **dołącz Snapshot Debugger** dla maszyny wirtualnej usługi IIS zostaną automatycznie uruchomione ponownie.
    > Po pierwszym wybraniu opcji **dołącz Snapshot Debugger** do Virtual Machine Scale Sets wymagane jest ręczne uaktualnienie każdego wystąpienia Virtual Machine Scale Sets.

    > [!NOTE]
    > (Program Visual Studio 2019 w wersji 16,2 lub nowszej) Snapshot Debugger włączono obsługę chmury platformy Azure. Upewnij się, że wybrane konto usługi Azure Resource i Azure Storage znajdują się w tej samej chmurze. Jeśli masz pytania dotyczące konfiguracji [zgodności platformy Azure](https://azure.microsoft.com/overview/trusted-cloud/) w przedsiębiorstwie, skontaktuj się z administratorem platformy Azure.

    Metadane dla **modułów** nie będą początkowo aktywowane, przejdź do aplikacji sieci Web, a przycisk **Rozpocznij zbieranie** stanie się aktywny. Program Visual Studio jest teraz w trybie debugowania migawek.

    ![Tryb debugowania migawek](../debugger/media/snapshot-message.png)

    > [!NOTE]
    > W przypadku VMSS użytkownik musi ręcznie uaktualnić wystąpienia w ich Virtual Machine Scale Sets po pierwszym dołączeniu Snapshot Debugger.

    Okno **moduły** pokazuje, kiedy wszystkie moduły zostały załadowane do zestawu skalowania maszyn wirtualnych Azure Machine\Virtual (wybierz polecenie **debuguj > modułów > systemu Windows** , aby otworzyć to okno).

    ![Sprawdź okno modułów](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>Ustaw punkt przyciągania

1. W edytorze kodu kliknij lewy odstęp obok wiersza kodu, który interesuje Cię, aby ustawić punkt przyciągania. Upewnij się, że kod jest już wykonywany.

    ![Ustaw punkt przyciągania](../debugger/media/snapshot-set-snappoint.png)

1. Kliknij pozycję **Rozpocznij zbieranie** , aby włączyć punkt przyciągania.

    ![Włącz punkt przyciągania](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > Nie można wykonać kroku podczas wyświetlania migawki, ale można umieścić wiele punkty przyciągania w kodzie, aby śledzić wykonywanie w różnych wierszach kodu. Jeśli masz wiele punkty przyciągania w kodzie, Snapshot Debugger upewnij się, że odpowiednie migawki pochodzą z tej samej sesji użytkownika końcowego. Snapshot Debugger robi to nawet wtedy, gdy w aplikacji jest wielu użytkowników.

## <a name="take-a-snapshot"></a>Tworzenie migawki

Po ustawieniu punkt przyciągania można ręcznie wygenerować migawkę, przechodząc do widoku przeglądarki witryny sieci Web i uruchamiając wiersz kodu lub poczekaj, aż użytkownicy generują je na podstawie ich użycia.

## <a name="inspect-snapshot-data"></a>Sprawdzanie danych migawek

1. Po trafieniu punkt przyciągania zostanie wyświetlona migawka w oknie narzędzia diagnostyczne. Aby otworzyć to okno, wybierz **debuguj > Windows > pokaż narzędzia diagnostyczne**.

    ![Otwórz punkt przyciągania](../debugger/media/snapshot-diagsession-window.png)

1. Kliknij dwukrotnie punkt przyciągania, aby otworzyć migawkę w edytorze kodu.

    ![Sprawdzanie danych migawek](../debugger/media/snapshot-inspect-data.png)

    Z tego widoku można przesuwać się nad zmiennymi, aby wyświetlać etykietki danych, korzystać z okien zmiennych **lokalnych**, **zegarki** i **stosu wywołań** , a także szacować wyrażenia.

    Sama witryna sieci Web jest nadal na żywo, a użytkownicy końcowi nie mają do nich wpływu. Tylko jedna migawka jest domyślnie przechwytywana na punkt przyciągania: Po przechwyceniu migawki punkt przyciągania wyłączone. Jeśli chcesz przechwycić kolejną migawkę w punkt przyciągania, możesz włączyć punkt przyciągania ponownie, klikając polecenie **Aktualizuj kolekcję**.

Możesz również dodać więcej punkty przyciągania do aplikacji i włączyć je przy użyciu przycisku **Aktualizuj kolekcję** .

**Potrzebujesz pomocy?** Zapoznaj się z tematami [Rozwiązywanie problemów i znanych problemów](../debugger/debug-live-azure-apps-troubleshooting.md) oraz [często zadawanych pytań dotyczących debugowania migawek](../debugger/debug-live-azure-apps-faq.md) .

## <a name="set-a-conditional-snappoint"></a>Ustaw punkt przyciągania warunkowe

Jeśli nie można ponownie utworzyć określonego stanu w aplikacji, należy rozważyć użycie warunkowej punkt przyciągania. Warunkowe punkty przyciągania ułatwiają kontrolowanie, kiedy należy wykonać migawkę, na przykład gdy zmienna zawiera konkretną wartość, którą chcesz sprawdzić. Można ustawić warunki przy użyciu wyrażeń, filtrów lub liczby trafień.

#### <a name="to-create-a-conditional-snappoint"></a>Aby utworzyć punkt przyciągania warunkowe

1. Kliknij prawym przyciskiem myszy ikonę punkt przyciągania (kulka pusta) i wybierz pozycję **Ustawienia**.

   ![Wybierz Ustawienia](../debugger/media/snapshot-snappoint-settings.png)

1. W oknie Ustawienia punkt przyciągania wpisz wyrażenie.

   ![Wpisz wyrażenie](../debugger/media/snapshot-snappoint-conditions.png)

   Na powyższej ilustracji migawka jest wykonywana tylko dla punkt przyciągania, kiedy `visitor.FirstName == "Dan"` .

## <a name="set-a-logpoint"></a>Ustaw punkt rejestrowania

Oprócz tworzenia migawek, gdy punkt przyciągania jest trafień, można także skonfigurować punkt przyciągania do rejestrowania wiadomości (to oznacza, że utworzono punkt rejestrowania). Możesz ustawić punkty rejestrowania bez konieczności ponownego wdrażania aplikacji. Punkty rejestrowania są wykonywane praktycznie i nie powodują wpływu ani efektów ubocznych działającej aplikacji.

#### <a name="to-create-a-logpoint"></a>Aby utworzyć punkt rejestrowania

1. Kliknij prawym przyciskiem myszy ikonę punkt przyciągania (niebieska sześciokąt), a następnie wybierz pozycję **Ustawienia**.

1. W oknie Ustawienia punkt przyciągania wybierz pozycję **Akcje**.

    ![Utwórz punkt rejestrowania](../debugger/media/snapshot-logpoint.png)

1. W polu **komunikat** można wprowadzić nowy komunikat dziennika, który ma być zalogowany. Możesz również obliczyć zmienne w komunikacie dziennika, umieszczając je w nawiasach klamrowych.

    W przypadku wybrania opcji **Wyślij do okno dane wyjściowe**, gdy zostanie trafiony punkt rejestrowania, komunikat pojawi się w oknie narzędzia diagnostyczne.

    ![Punkt rejestrowania dane w oknie narzędzia diagnostyczne](../debugger/media/snapshot-logpoint-output.png)

    Jeśli wybierzesz pozycję **Wyślij do dziennika aplikacji**, gdy punkt rejestrowania zostanie trafiony, komunikat pojawi się w dowolnym miejscu, w którym można zobaczyć komunikaty z `System.Diagnostics.Trace` (lub `ILogger` w programie .NET Core), takie jak [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs).

## <a name="next-steps"></a>Następne kroki

W tym samouczku przedstawiono sposób korzystania z Snapshot Debugger dla Virtual Machines platformy Azure i Virtual Machine Scale Sets platformy Azure. Możesz chcieć przeczytać więcej szczegółowych informacji na temat tej funkcji.

> [!div class="nextstepaction"]
> [Debugowanie migawek — często zadawane pytania](../debugger/debug-live-azure-apps-faq.md)
