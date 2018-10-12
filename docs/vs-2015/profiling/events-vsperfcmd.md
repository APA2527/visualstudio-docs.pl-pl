---
title: Zdarzenia (VSPerfCmd) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b67fbdb021cb39edd8899d537db368c18a6421ff
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49215276"
---
# <a name="events-vsperfcmd"></a>Zdarzenia (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPerfCmd.exe **zdarzenia** opcja kontroluje rejestrowanie zdarzeń śledzenia dla Windows (ETW). Dane funkcji ETW są zapisywane w pliku etl, który jest oddzielony od plików danych profilera. Dane mogą być wyświetlane w raporcie przy użyciu [VSPerfReport](../profiling/vsperfreport.md) polecenia/Summary: ETW.  
  
 **Zdarzenia** opcji można wywołać w dowolnym momencie przed VSPerfCmd **zamknięcia** polecenia jest wywoływana, aby zatrzymać profilowanie.  
  
## <a name="syntax"></a>Składnia  
  
```  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametry  
 **Na**&#124;**wyłączone**  
 Uruchamia lub zatrzymuje zbieranie danych zdarzeń.  
  
 `Guid`  
 Identyfikator GUID kontrolki dostawcy.  
  
 `ProviderName`  
 Nazwa dostawcy, który jest zarejestrowany za pomocą Instrumentacji zarządzania Windows (WMI).  
  
 `Flags`  
 "0 x" — prefiks wartość szesnastkową znaczników, który jest definiowany przez dostawcę zdarzeń.  
  
 `Level`  
 Określa ilość zebranych danych. `Level` jest definicją Dostawca zdarzeń.  
  
 **Zdarzenia** opcja obsługuje następujące słowa kluczowe jądra jako nazwy dostawcy:  
  
 **Proces**  
 Przetwarzanie zdarzeń  
  
 **Wątek**  
 Zdarzenia wątków  
  
 **Obraz**  
 Obraz ładowanie i zwalnianie zdarzenia  
  
 **Dysk**  
 Zdarzenia We/Wy dysku  
  
 **Plik**  
 Zdarzenia We/Wy plików  
  
 **Hardfault**  
 Sprzętowe błędy stron  
  
 **Pagefault**  
 Słabe strony błędów  
  
 **Sieci**  
 Zdarzenia sieci  
  
 **Registry**  
 Zdarzenia dostępu do rejestru  
  
 Należy pamiętać, że dostawca jądra można włączyć tylko. Nie można wyłączyć, ani jej flag można modyfikować, dopóki nie wyłącza monitor.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
>  Po włączeniu zdarzeń CLR ETW uruchamiania dodatkowe są zbierane również w raporcie widoku śledzenia. Aby wykluczyć zdarzenia uruchamiania były wyświetlane w raporcie, użyj następującego polecenia:  
  
```  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Jeśli nie wykluczysz zdarzenia uruchamiania, następnie ponieważ te zdarzenia nie są wymienione w pliku Managed Object Format (MOF), zostaną one wyświetlone jako identyfikatory GUID w raporcie. Aby uzyskać więcej informacji, zobacz tę stronę w witrynie sieci Web firmy Microsoft: [plik przykładowy Managed Object Format (MOF)](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Zobacz też  
 [Narzędzia VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilowanie aplikacji autonomicznych](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilowanie aplikacji sieci Web platformy ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Usługi profilowania](../profiling/command-line-profiling-of-services.md)



