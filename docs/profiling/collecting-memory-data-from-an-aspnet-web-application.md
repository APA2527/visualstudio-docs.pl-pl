---
title: Zbieranie danych pamięci z aplikacji internetowej ASP.NET przy użyciu wiersza polecenia Profiler | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- profiling tools,.NET memory method
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: c99ca461acc51697a8c5b654f5b350149ac76c09
ms.sourcegitcommit: 8d38d5d2f2b75fc1563952c0d6de0fe43af12766
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/26/2018
ms.locfileid: "39276292"
---
# <a name="collect-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line"></a>Zbieranie danych pamięci z aplikacji sieci web ASP.NET przy użyciu wiersza polecenia profilera
W tej sekcji opisano procedury składowane i opcji zbierania danych pamięci alokacji i obiekt okresu istnienia dla aplikacji sieci Web platformy ASP.NET za pomocą **VSPerfCmd** narzędzie wiersza polecenia.  
  
> [!NOTE]
>  **VSPerfCmd** narzędzie zapewnia pełny dostęp do funkcji narzędzi profilowania, między innymi wstrzymywanie i wznawianie profilowania i zbieranie dodatkowych danych z procesora i liczniki wydajności Windows. Można również użyć **VSPerfASPNETCmd** narzędzie wiersza polecenia, jeśli nie potrzebujesz tej funkcji. W porównaniu z [VSPerfCmd](../profiling/vsperfcmd.md) narzędzia wiersza polecenia, żadne zmienne środowiskowe, które należy skonfigurować i ponowne uruchomienie komputera nie jest wymagane. Aby uzyskać więcej informacji, zobacz [profilowania szybkie witryn sieci web za pomocą polecenia VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Wspólne zadania
  
|Zadanie|Powiązana zawartość|  
|----------|---------------------|  
|**Dołącz profiler do działającej aplikacji platformy ASP.NET**|-   [Porady: dołączanie profilera do aplikacji sieci web ASP.NET do zbierania danych pamięci](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|  
|**Instrument statycznie skompilowane pliki binarne**|-   [Porady: Instrumentacja statycznie skompilowanej aplikacji ASP.NET i zbieranie danych pamięci](../profiling/how-to-instrument-a-statically-compiled-aspnet-app-and-collect-memory-data.md)|  
|**Instrument dynamicznie skompilowanych plików binarnych**|-   [Porady: Instrumentacja dynamicznie skompilowanej aplikacji ASP.NET i zbieranie danych pamięci](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)|  
  
## <a name="related-tasks"></a>Zadania powiązane
  
### <a name="profile-aspnet-web-applications"></a>Aplikacje sieci web ASP.NET profilu  
  
|Zadanie|Powiązana zawartość|  
|----------|---------------------|  
|**Profil przy użyciu metody próbkowania**|-   [Zbieranie statystyk aplikacji przy użyciu metody próbkowania](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**Profil przy użyciu metody Instrumentacji**|-   [Zbieranie szczegółowych danych o chronometrażu przy użyciu metody Instrumentacji](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|  
|**Profil działanie zasobu rywalizacji o zasoby i wątku**|-   [Zbieranie danych współbieżności](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="profile-net-framework-memory-data"></a>Profil danych pamięci .NET Framework  
  
|Zadanie|Powiązana zawartość|  
|----------|---------------------|  
|**Profil aplikacji autonomicznej (klienta)**|-   [Zbieranie danych pamięci .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|  
|**Usługi profilowania**|-   [Zbieranie danych pamięci .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="analyze-net-memory-data-views-and-reports"></a>Analizowanie widoki danych pamięci .NET i raporty  
 [Widoki danych pamięci .NET](../profiling/dotnet-memory-data-views.md)  
  
## <a name="reference"></a>Tematy pomocy  
 [Narzędzia profilowania wiersza polecenia — dokumentacja](../profiling/command-line-profiling-tools-reference.md)