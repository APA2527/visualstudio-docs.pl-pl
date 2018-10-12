---
title: Wymaga autoryzacji serwera proxy | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2650dadddefe3be18a4406eb4fd07c5599622212
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259218"
---
# <a name="proxy-authorization-required"></a>Wymaga autoryzacji serwera proxy
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Ten błąd występuje zazwyczaj, gdy użytkownicy są połączeni do programu Visual Studio Online za pośrednictwem serwera proxy i serwer proxy blokuje wywołania. Visual Studio Online jest używany do przechowywania użytkownik zalogowany do środowiska IDE.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Uruchom ponownie program Visual Studio. Powinna zostać wyświetlona okno dialogowe uwierzytelniania serwera proxy. Wprowadź swoje poświadczenia w oknie dialogowym.  
  
-   Jeśli powyższy krok nie rozwiąże problemu, może to być spowodowane serwera proxy nie jest wyświetlany monit o poświadczenia dla http://go.microsoft.com adresy, ale jest to spowodowane *. adresów visualStudio.com. Na tych serwerach należy umieścić na liście dozwolonych poniżej, aby odblokować wszystkie w scenariuszach logowania w programie Visual Studio:  
  
    -   *.windows.net  
  
    -   *.microsoftonline.com  
  
    -   *.visualstudio.com  
  
    -   *.microsoft.com  
  
    -   *.live.com  
  
-   W przeciwnym razie możesz usunąć http://go.microsoft.com adresów z listy dozwolonych adresów, tak, aby w oknie dialogowym uwierzytelniania serwera proxy, pojawia się dla obu http://go.microsoft.com adres i punkty końcowe serwera, po ponownym uruchomieniu programu Visual Studio.  
  
-   LUB  
  
-   Poświadczenia domyślne za pomocą serwera proxy, należy wykonać następujące:  
  
    1.  Znajdź devenv.exe.config (plik devenv.exe w konfiguracji): **%ProgramFiles%\Microsoft Visual Studio 14.0\Common7\IDE** (lub **% ProgramFiles (x86) %\Microsoft Visual Studio 14.0\Common7\IDE**) .  
  
    2.  Plik konfiguracyjny zawiera `<system.net>` zablokować, a następnie dodaj następujący kod:  
  
        ```xml  
        <defaultProxy enabled="true" useDefaultCredentials="true">  
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>  
        </defaultProxy>  
  
        ```  
  
         Adres serwera proxy poprawne należy wstawić dla sieci w `proxyaddress="<http://<yourproxy:port#>`.  
  
-   LUB  
  
-   Można również postępuj zgodnie z instrukcjami [ten wpis](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) można dodać kod, który umożliwi używanie serwera proxy.



