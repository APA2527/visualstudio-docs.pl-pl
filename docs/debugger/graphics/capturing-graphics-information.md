---
title: Przechwytywanie informacji graficznych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.frame
- vs.graphics.capturewindow
- VS.ToolsOptionsPages.Graphics_Diagnostics.Capture
ms.assetid: 187ce86e-e340-4f6c-8937-8e8f1027a17f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09571f593c77ffed1daaeaa2ac7639e2a97a32ea
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49820528"
---
# <a name="capturing-graphics-information"></a>Przechwytywanie informacji graficznych
Przechwytywać informacje graficzne z aplikacji Direct3D, tak aby analizator grafiki programu Visual Studio można użyć do diagnozowania problemów z renderowaniem i problemy z wydajnością.  
  
## <a name="capturing-graphics-information"></a>Przechwytywanie informacji graficznych  
 Przechwytywanie informacji graficznych jest procesem dwuetapowym. Po pierwsze, uruchom aplikację w obszarze Diagnostyka grafiki, a następnie określ jedną lub więcej ramek, z których zostaną przechwycone szczegółowe informacje.  
  
### <a name="to-run-your-app-under-graphics-diagnostics"></a>Aby uruchomić aplikację w obszarze Diagnostyka grafiki  
  
- Na pasku menu wybierz **debugowania**, **grafiki**, **Rozpocznij debugowanie grafiki**. (Klawiatura: naciśnij klawisze Alt+F5)  
  
- Na **grafiki** narzędzi, wybierz **Rozpocznij debugowanie grafiki** przycisku.  
  
  Gdy aplikacja jest uruchomiona w ramach diagnostyki grafiki, pewne rodzaje informacji graficznych są cały czas przechwytywane; obejmuje to konfigurację urządzenia, tworzenie łańcucha wymiany elementów, tworzenie grafiki, obiektów i zasobów oraz inne ważne wydarzenia, które wpływają na więcej niż jedną klatkę. W tym samym czasie można przechwycić szczegółowe informacje na temat konkretnych klatek. Dotyczy to wywołania rysowań i wysyłań cieniowania obliczenia, wraz z obiektami i zasobami Direct3D, które je obsługują.  
  
### <a name="to-capture-a-frame"></a>Aby przechwycić ramkę  
  
- W programie Visual Studio na **grafiki** narzędzi, kliknij przycisk **Przechwyć ramkę** przycisk ![ikony przycisku przechwytywania grafiki](media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics").  
  
- Na klawiaturze naciśnij klawisz Print Screen.
  
  > [!NOTE]
  >  Gdy aplikacja jest uruchomiona w ramach **Graphics Diagnostics**, klawisz Print Screen należy używać tylko do przechwytywania informacji graficznych; nie wykonuje swojego normalnego działania. To pozostaje, dopóki nie zatrzymasz przechwytywania informacji graficznych — zwykle przez zatrzymanie debugowania lub normalne wyjście z aplikacji — nawet wtedy, gdy fokus jest na innej aplikacji.  
  
- W interfejsie przechwytywania programu Visual Studio, należy wybrać **Przechwyć ramkę** znajdujący się poniżej **sesji diagnostycznej** osi czasu, lub wybierz dużych **Przechwyć ramkę** przycisku znajdujący się poniżej **klatek na sekundę** torach pływackich i w prawo wszystkie wcześniej przechwycone ramki. Przyciski są wyróżnione na poniższej ilustracji.  
  
   ![Przechwytywanie ramki za pomocą narzędzia użycie procesora GPU.](media/pix_gpu_usage_tool_capture_frame.png)  
  
   Gdy wszystko będzie gotowe zbadać ramki zostało przechwycone, zacznij **analizatora grafiki programu Visual Studio** wykonując **klatek...**  link powyżej miniatury obrazów lub przez dwukrotne kliknięcie miniatury.  
  
  Tylko całe ramki mogą być przechwytywane, więc po zainicjowaniu przechwytywania tak naprawdę to informacje grafiki z następnej ramki są rejestrowane. Zapisywanie rozpoczyna się natychmiast po zaprezentowaniu klatki, w której rozpocząłeś przechwytywanie, i kończy się po zaprezentowaniu przechwyconej klatki. Możesz przechwycić tyle klatek, ile chcesz, gdy aplikacja jest uruchomiona w ramach diagnostyki grafiki. Jeśli nie przechwycisz żadnej ramki, dziennik grafiki jest odrzucany.  
  
  Podczas przechwytywania ramki, Visual Studio wyświetli okno (.diagsession) sesji diagnostyki. Jeśli zamknąć to okno, Zatrzymaj debugowanie lub zamknąć aplikację, nie może przechwytywać więcej ramek do tego dziennika. Do przechwytywania informacji graficznych, musisz uruchomić aplikację w obszarze Diagnostyka grafiki ponownie, aby rozpocząć nową sesję diagnostyki.  
  
### <a name="graphics-diagnostics-capture-options"></a>Opcje przechwytywania diagnostyki grafiki  
 Można skonfigurować przechwytywania Zbieraj stosy wywołań dla wszystkich zdarzeń grafiki lub być podzbiorem ograniczone, wyłącz Przechwytywanie HUD oraz włączyć lub wyłączyć tryb zgodności przechwytywania.  
  
#### <a name="to-configure-graphics-diagnostics-capture-options"></a>Aby skonfigurować opcje przechwytywania diagnostyki grafiki  
  
1.  Na pasku menu wybierz menu Narzędzia, opcje. Zostanie wyświetlone okno dialogowe Opcje.  
  
2.  Na liście Kategoria opcji po lewej stronie wybierz pozycję Diagnostyka grafiki, a następnie skonfiguruj żądane opcje diagnostyki grafiki.  
  
     **Zbieraj stosy wywołań podczas przechwytywania (zwalnia przechwytywanie)**  
     Zaznacz to pole, aby zebrać stosy wywołań. Stosy wywołań nie są zbierane domyślnie. Aby przechwycić stosy wywołań, upewnij się, że **zbieranie wywołań stosów podczas przechwytywania (zwalnia Przechwytywanie** pole wyboru jest ustawiona na włączanie kolekcji, a następnie ustaw opcję **znaczników rysowania, wysyłania, obecny i wydajności**opcję (ustawienie domyślne), aby zbierać tylko najważniejsze stosy wywołań, lub **wszystko** opcję, aby zbierać wszystkie stosy wywołań. Aby zatrzymać zbieranie stosy wywołań później, należy wyczyścić **zbieranie wywołań stosów podczas przechwytywania (zwalnia Przechwytywanie** pola wyboru.  
  
     **Wyłącz HUD w grze podczas przechwytywania**  
     Sprawdź, czy to pole, aby wyłączyć HUD nakładki aplikacji działających w ramach graphics diagnostics zwykle wyświetla. Usuń zaznaczenie pola wyboru go, aby wyświetlić nakładkę HUD.  
  
     **Przechwyć w trybie zgodności**  
     Zaznacz to pole, aby przechwytywać informacje graficzne w trybie zgodności. Przechwytywanie w trybie zgodności jest ustawieniem domyślnym. W trybie zgodności Direct3D nie będzie zgłaszać, czy procesor GPU obsługuje wszystkie dodatkowe funkcje, poza tymi określonymi w poziomie podstawowych funkcji. Zapobiega aplikacji jest przechwytywane przy użyciu rozszerzeń specyficznych dla sprzętu z procesorem GPU jego przechwycone w to i gwarantuje, że dziennik grafiki można odtwarzać ponownie za pomocą dowolnego procesora GPU, który obsługuje funkcję tego samego lub wyższego poziomu. Usuń zaznaczenie tego pola, aby wyłączyć tryb zgodności; Dzienniki przechwycić przy użyciu wyłączono tryb zgodności zakończy się niepowodzeniem do odtwarzania na dowolnym procesora GPU, który nie obsługuje tego samego dodatkowe funkcje, które były używane przez aplikację podczas przechwytywania.  
  
     **Zatrzymaj przechwytywanie, jeśli zostaną znalezione jakiekolwiek błędy warstw zestawu SDK**  
     Zaznacz to pole, aby natychmiast zatrzymać przechwytywania, jeśli zostaną napotkane błędy.  
  
## <a name="capturing-graphics-information-remotely"></a>Zdalne przechwytywanie informacji graficznych  
 Informacje graficzne mogą być przechwytywane z aplikacji, która jest uruchomiona na komputerze lokalnym lub na zdalnym komputerze lub urządzeniu. Zdalne przechwytywanie jest obsługiwane dla [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)] maszyn i [!INCLUDE[winblue_winrt_2](../includes/winblue_winrt_2_md.md)] urządzeń. Aby przechwytywać informacje graficzne z aplikacji, która jest uruchomiona zdalnie, skonfiguruj projekt dla zdalnego debugowania, a następnie uruchom aplikację w obszarze Diagnostyka grafiki zgodnie z wcześniejszym opisem. Aplikacja jest uruchamiana na komputerze zdalnym, a przechwycone informacje graficzne są rejestrowane na komputerze deweloperskim.  
  
 Konfiguracja projektu dla zdalnego debugowania zależy od rodzaju aplikacji, którą projektujesz, i języka programowania, którego używasz. Aby uzyskać informacje o tym, jak skonfigurować zdalne debugowanie aplikacji platformy uniwersalnej systemu Windows, zobacz [uruchamianie aplikacji platformy UWP na komputerze zdalnym](../run-windows-store-apps-on-a-remote-machine.md). Aby uzyskać informacje o tym, jak skonfigurować zdalne debugowanie klasycznych aplikacji Windows, zobacz [zdalne debugowanie](../remote-debugging.md).  
  
 Później można użyć zdalnego komputera lub urządzenia do odtwarzania informacji graficznych, bez względu na to, gdzie informacje zostały przechwycone. Aby uzyskać więcej informacji, zobacz [porady: zmiana maszyny odtwarzania diagnostyki grafiki](how-to-change-the-graphics-diagnostics-playback-machine.md).  
  
## <a name="capturing-graphics-information-from-the-command-line"></a>Przechwytywanie informacji graficznych, z poziomu wiersza polecenia  
 Informacje graficzne mogą być przechwytywane z aplikacji za pomocą narzędzia wiersza polecenia. To narzędzie DXCap.exe, można szybko przechwytywania i odtwarzania informacji graficznych bez korzystania z programu Visual Studio lub przechwytywanie programistyczne. W szczególności DXCap.exe można użyć w przypadku usługi automation lub w środowisku testowym. Aby uzyskać więcej informacji na temat DXCap.exe zobacz [narzędzia wiersza polecenia do przechwytywania](command-line-capture-tool.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Przewodnik: przechwytywanie informacji graficznych](walkthrough-capturing-graphics-information.md)