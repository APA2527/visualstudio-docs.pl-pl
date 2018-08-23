---
title: Korzystanie z kontrolek HTML5 w kodowanych testów interfejsu użytkownika | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2000b214-ae92-4334-b549-aa0eb4f45fe1
caps.latest.revision: 19
ms.author: gewarren
manager: douge
ms.openlocfilehash: 14bdab12cf241914d1f41581ae5434ae1776ec2b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681857"
---
# <a name="using-html5-controls-in-coded-ui-tests"></a>Korzystanie z kontrolek HTML5 w kodowanych testach interfejsu użytkownika
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [za pomocą kontrolek HTML5 w kodowanych testach interfejsu użytkownika](https://docs.microsoft.com/visualstudio/test/using-html5-controls-in-coded-ui-tests).  
  
Kodowane testy interfejsu użytkownika obsługują niektóre formanty języka HTML5, które są dołączone do programu Internet Explorer 9 i Internet Explorer 10.  
  
 **Wymagania**  
  
-   Visual Studio Enterprise  
  
> [!WARNING]
>  W wersjach wcześniejszych niż Internet Explorer 10 było możliwe do uruchomienia kodowanych testów interfejsu użytkownika w porównaniu do programu proces programu Internet Explorer wyższym poziomie uprawnień. Podczas uruchamiania kodowanych testów interfejsu użytkownika w programie Internet Explorer 10, proces programu Internet Explorer i kodowany test interfejsu użytkownika musi być na tym samym poziomie uprawnień. Jest to ze względu na bardziej bezpieczne funkcje kontenera aplikacji w programie Internet Explorer 10.  
  
> [!WARNING]
>  Jeśli tworzysz kodowane testy interfejsu użytkownika w programie Internet Explorer 10, może nie zostać uruchomiony za pomocą programu Internet Explorer 9 i Internet Explorer 8. Jest to spowodowane programu Internet Explorer 10 zawiera formanty HTML5, takie jak Audio, wideo, pasek postępu i suwak. Te formanty HTML5 nie są rozpoznawane przez Internet Explorer 9 i Internet Explorer 8. Podobnie test interfejsu użytkownika kodowany za pomocą Internet Explorer 9 może zawierać niektóre formanty języka HTML5, które również nie zostaną rozpoznane przez Internet Explorer 8.  
  
## <a name="supported-html5-controls"></a>Formanty HTML5 obsługiwane  
 Kodowane testy interfejsu użytkownika obsługują rekordu, odtwarzanie i sposób sprawdzania poprawności formantów HTML5, następujące:  
  
-   [Audio Control](#UsingHTML5ControlsCodedUITestsAudio)  
  
-   [Kontrolki wideo](#UsingHTML5ControlsCodedUITestsVideo)  
  
-   [Slider](#UsingHTML5ControlsCodedUITestsSlider)  
  
-   [ProgressBar](#UsingHTML5ControlsCodedUITestsProgressBar)  
  
###  <a name="UsingHTML5ControlsCodedUITestsAudio"></a> Audio Control  
 **Kontrolki dźwięku:** poprawnie zarejestrowane i odtwarzać akcji sterowanie dźwięk HTML5.  
  
 ![Dźwięk HTML5 kontroli](../test/media/codedui-html5-audio.png "CodedUI_HTML5_Audio")  
  
|Akcja|Rejestrowanie|Wygenerowany kod|  
|------------|---------------|--------------------|  
|**Odtwórz dźwięk**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Odtwórz \<name > Audio z zakresu od 00:00:00|HtmlAudio.Play(TimeSpan)|  
|**Starać się w określonym czasie które usłyszysz**|Wyszukiwanie \<name > Audio do 00:01:48|HtmlAudio.Seek(TimeSpan)|  
|**Wstrzymaj audio**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Wstrzymaj \<name > Audio na 00:01:53|HtmlAudio.Pause(TimeSpan)|  
|**Wycisz audio**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Wycisz \<name > Audio|HtmlAudio.Mute()|  
|**Wyłącz Wyciszenie audio**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Wyłącz wyciszenie \<name > Audio|HtmlAudio.Unmute()|  
|**Zmień głośność dźwięku**|Ustaw głośność \<name > Audio do 79%|HtmlAudio.SetVolume(float)|  
  
 Następujące właściwości są dostępne dla HtmlAudio i można dodać potwierdzenia na wszystkich z nich:  
  
```  
string AutoPlay  
string Controls  
string CurrentSrc  
string CurrentTime  
string CurrentTimeAsString  
string Duration  
string DurationAsString  
string Ended  
string Loop  
string Muted  
string Paused  
string PlaybackRate  
string ReadyState  
string Seeking  
string Src  
string Volume  
  
```  
  
 **Właściwości wyszukiwania:** właściwości wyszukiwania `HtmlAudio` są `Id`, `Name` i `Title`.  
  
 **Właściwości filtru:** właściwości filtru dla `HtmlAudio` są `Src`, `Class`, `ControlDefinition` i `TagInstance`.  
  
> [!NOTE]
>  Ilość czasu, która umożliwia wyszukiwanie i wstrzymywanie działania mogą być znaczące. Podczas odtwarzania kodowanego testu interfejsu użytkownika będzie czekać aż do określonej w `(TimeSpan)` przed wstrzymaniem audio. Jeśli przez kilka specjalnych okoliczności określonego czasu minęło przed osiągnięcia polecenie wstrzymania, zostanie zgłoszony wyjątek.  
  
###  <a name="UsingHTML5ControlsCodedUITestsVideo"></a> Kontrolki wideo  
 **Kontrolki wideo:** poprawnie zarejestrowana i odtwarzać akcji dla kontrolki wideo HTML5.  
  
 ![Kontrolki wideo HTML5](../test/media/codedui-html5-video.png "CodedUI_HTML5_Video")  
  
|Akcja|Rejestrowanie|Wygenerowany kod|  
|------------|---------------|--------------------|  
|**Odtwórz wideo**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Odtwórz \<name > wideo z zakresu od 00:00:00|HtmlVideo.Play(TimeSpan)|  
|**Starać się w określonym czasie, w trakcie filmu wideo**|Wyszukiwanie \<name > film, aby 00:01:48|HtmlVideo.Seek(TimeSpan)|  
|**Wstrzymaj wideo**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Wstrzymaj \<name > wideo o 00:01:53|HtmlVideo.Pause(TimeSpan)|  
|**Wycisz wideo**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Wycisz \<name > wideo|HtmlVideo.Mute()|  
|**Wyłącz Wyciszenie wideo**<br /><br /> Bezpośrednio z kontroli lub z menu kontekstowego kontrolki.|Wyłącz wyciszenie \<name > wideo|HtmlVideo.Unmute()|  
|**Zmień ilość wideo**|Ustaw głośność \<name > wideo do 79%||  
  
 Wszystkie właściwości HtmlAudio są dostępne dla HtmlVideo. Ponadto następujące trzy właściwości również są dostępne. Można dodać potwierdzenia na wszystkich z nich.  
  
```  
string Poster  
string VideoHeight  
string VideoWidth  
  
```  
  
 **Właściwości wyszukiwania:** właściwości wyszukiwania `HtmlVideo` są `Id`, `Name` i `Title`.  
  
 **Właściwości filtru:** właściwości filtru dla `HtmlVideo` są `Src`, `Poster`, `Class`, `ControlDefinition` i `TagInstance`.  
  
> [!NOTE]
>  Jeśli przewinąć do tyłu lub szybkie przewijanie do przodu wideo przy użyciu etykiet-30s lub +30s, to zostaną zagregowane się w odpowiednim czasie.  
  
###  <a name="UsingHTML5ControlsCodedUITestsSlider"></a> Suwak  
 **Kontrolka Slider:** poprawnie rejestrowane i odtwarzać akcji w kontrolce suwaka HTML5.  
  
 ![Kontrolka suwaka HTML5](../test/media/codedui-html5-slider.png "CodedUI_HTML5_Slider")  
  
|Akcja|Rejestrowanie|Wygenerowany kod|  
|------------|---------------|--------------------|  
|**Ustaw położenie na suwaku**|Ustaw położenie \<x > w \<name > suwaka|HtmlSlider.ValueAsNumber=\<x>|  
  
 Następujące właściwości są dostępne dla HtmlSlider i można dodać potwierdzenia na wszystkich z nich:  
  
```  
string Disabled  
string Max  
string Min  
string Required  
string Step  
string ValueAsNumber  
```  
  
###  <a name="UsingHTML5ControlsCodedUITestsProgressbar"></a> Pasek postępu  
 **Kontrolka ProgreesBar:** ProgressBar jest formantem interactable. Można dodać asercje `Value` i `Max` właściwości tej kontrolki.  
  
 ![HTML5 ProgressBar, kontrolka](../test/media/codedui-html5-progressbar.png "CodedUI_HTML5_ProgressBar")  
  
## <a name="see-also"></a>Zobacz też  
 [Elementy HTML](http://go.microsoft.com/fwlink/?LinkID=232441)   
 [Używanie automatyzacji interfejsu użytkownika do testowania kodu](../test/use-ui-automation-to-test-your-code.md)   
 [Tworzenie kodowanych testów interfejsu użytkownika](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Dostosowywanie kodowanego testu interfejsu użytkownika](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeCUITModify)   
 [Obsługiwane konfiguracje oraz platformy zakodowanych testów interfejsu użytkownika i rejestrowania akcji](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)



