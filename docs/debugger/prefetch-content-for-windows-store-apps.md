---
title: Debugowanie za pomocą pobieranych z wyprzedzeniem zawartości w aplikacjach platformy uniwersalnej systemu Windows | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: d511934dc185ed6dac8034ee3e149391b2dd185e
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281549"
---
# <a name="debug-uwp-apps-using-prefetched-content-in-visual-studio"></a>Debugowanie aplikacji platformy UWP przy użyciu pobieranych z wyprzedzeniem zawartości w programie Visual Studio
  
 Aby zapewnić zwiększyć szybkość reakcji aplikacji platformy uniwersalnej systemu Windows, możesz poprosić o Windows do wstępnego ładowania niektórych zawartości sieci web, takich jak strony sieci web lub obrazów do aplikacji [WinINet](/windows/desktop/WinInet/about-wininet) pamięci podręcznej. Ta funkcja jest wywoływana, trwa pobieranie z wyprzedzeniem. Jest szczególnie efektywna, dla zawartości, która jest używana podczas uruchamiania, ale użytkownik może zawartość pobrana z wyprzedzeniem inne często używane, za. Metody [Windows.Networking.BackgroundTransfer.ContentPrefetcher](/uwp/api/Windows.Networking.BackgroundTransfer.ContentPrefetcher) klasy umożliwiają określenie identyfikatorów URI zawartości, którą chcesz wstępnego ładowania. Zobacz zestaw SDK Windows [przykładowej zawartości pobierania z wyprzedzeniem](https://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309) przykładów dotyczących sposobów dodać funkcje ContentPrefetcher do aplikacji.  
  
 Windows korzysta z algorytmów heurystycznych, aby określić, gdy, a pobieranie z wyprzedzeniem powinny być wykonywane i jakie zasoby zostaną pobrane. Algorytm heurystyczny uwzględniać konto system sieci i stan zasilania, Historia użycia aplikacji użytkownika oraz liczbę prób wcześniejszego pobierania z wyprzedzeniem. W programie Visual Studio, można użyć **wyzwalacza Windows Store App pobieranie z wyprzedzeniem** polecenie, aby wymusić Windows umożliwia zignorowanie Algorytm heurystyczny ContentPrefetcher i wstępnego ładowania całą zawartość określona witryna sieci web. Może to być przydatne, jeśli chcesz, aby przetestować zachowanie aplikacji lub wydajność dzięki zawartość pobrana z wyprzedzeniem w znanym stanie (załadowane lub nie załadowano).  
  
## <a name="to-force-preloading-of-contentprefetcher-specified-resources"></a>Aby wymusić wstępne ładowanie ContentPrefetcher określone zasoby  
 Ta procedura zakłada, że masz już Ustawianie funkcji ContentPrefetcher i określony identyfikator URI zawartości do wstępnego w projekcie aplikacji. Aby wymusić wstępne ładowanie zawartości, gdy określone zasoby są nowe lub zmodyfikowane, musisz uruchomić i zatrzymać aplikację, przed wybraniem **wyzwalacza Windows Store App pobieranie z wyprzedzeniem** polecenia. Możesz uruchomić tę aplikację, aby najpierw zarejestrować identyfikatory URI. **Wyzwalanie pobierania z wyprzedzeniem programu Windows Store App** polecenie wymusza następnie ContentPrefetcher, aby pobrać zawartość i dodaj ją w pamięci podręcznej. W kolejnych uruchomień aplikacji można założyć, że zawartość jest wstępnie załadowane.  
  
1.  Uruchom aplikację, aby zarejestrować zawartość pobieranie z wyprzedzeniem identyfikatory URI z aplikacją. Na **debugowania** menu, wybierz **Rozpocznij debugowanie** (skrót klawiaturowy: F5).  
  
2.  Na **debugowania** menu, wybierz **Zatrzymaj debugowanie** (skrót klawiaturowy: Shift + F5).  
  
3.  Na **debugowania** menu, wybierz **inne cele debugowania** , a następnie wybierz **wyzwalacza Windows Store App pobieranie z wyprzedzeniem**.  
  
 Można teraz debugować, test lub analizowanie aplikacji przy użyciu zasobów internetowych pobieranych z wyprzedzeniem.  
  
> [!NOTE]
>  Powtórz te czynności przy dodawaniu lub zmodyfikować zawartość określona witryna sieci web.  
  
## <a name="see-also"></a>Zobacz też  
 [Wpis w blogu: wyzwalanie pobierania z wyprzedzeniem for Windows Store Apps w programie Visual Studio 2013 Update 2](https://blogs.msdn.microsoft.com/devops/2014/02/06/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2/)