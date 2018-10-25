---
title: VSPerf | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b5854e62-279e-4850-bfeb-0c6ef82f4805
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c841e6930db8f65aaf93c314359656689ecfd1c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49903546"
---
# <a name="vsperf"></a>VSPerf
Użyj **VsPerf** narzędzie wiersza polecenia do:  
  
1. Profilowanie aplikacji platformy uniwersalnej systemu Windows z poziomu wiersza polecenia, gdy program Visual Studio nie jest zainstalowany na urządzeniu.  
  
2. Profile, aplikacje klasyczne systemu Windows 8 i aplikacji systemu Windows Server 2012 za pomocą metoda profilowania próbkowanie.  
  
   Aby uzyskać więcej informacji na temat opcji profilowania, zobacz [narzędzia do oceny wydajności w aplikacjach systemu Windows 8 i Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="uwp-apps-only"></a>Tylko aplikacje platformy uniwersalnej systemu Windows  
 Te opcje są stosowane tylko do aplikacji platformy uniwersalnej systemu Windows.  
  
|||  
|-|-|  
|**App: {AppName}**|Uruchamia program profilujący i czeka, aż do określonej aplikacji, które mają zostać uruchomione z Start menu.<br /><br /> Uruchom `vsperf /listapps` Aby wyświetlić nazwę aplikacji i Pełna_nazwa_pakietu zainstalowanych aplikacji.|  
|**/ pakietu: {Pełna_nazwa_pakietu}**|Uruchamia program profilujący i czeka, aż do określonej aplikacji, które mają zostać uruchomione z Start menu.<br /><br /> Uruchom `vsperf /listapps` Aby wyświetlić nazwę aplikacji i Pełna_nazwa_pakietu zainstalowanych aplikacji.|  
|**/js**|Wymagane na potrzeby profilowania aplikacji JavaScript.<br /><br /> Zbieranie danych wydajności z aplikacji JavaScript.<br /><br /> Użyj tylko przy użyciu przełącznika/Package lub / dołączyć.|  
|**/noclr**|Opcjonalna. Nie zbieraj danych CLR.<br /><br /> Użyj tylko przy użyciu przełącznika/Package lub / dołączyć.<br /><br /> Optymalizacja, symboli zarządzanych, nie zostanie rozwiązany.|  
|**/listapps**|Lista zainstalowanych aplikacji, nazwy i PackageFullNames.|  
  
## <a name="windows-8-desktop-applications-and-windows-server-2012-applications-only"></a>Aplikacje klasyczne systemu Windows 8 i tylko w aplikacji systemu Windows Server 2012  
 Te opcje nie działają w aplikacjach platformy uniwersalnej systemu Windows.  
  
|||  
|-|-|  
|**/ uruchomienia: {pliku wykonywalnego}**|Rozpoczyna się i rozpoczyna się profilowanie określony plik wykonywalny.|  
|**przełącznika/args: {ExecutableArguments}**|Określa argumenty wiersza polecenia do przekazania **/uruchamianie** docelowej.|  
|**/ Console**|Przebiegi **/uruchamianie** elementu docelowego w nowym oknie polecenia.|  
  
## <a name="all-applications"></a>Wszystkie aplikacje  
 Te opcje stosowania się do aplikacji systemu Windows 8 lub Windows Server 2012.  
  
|||  
|-|-|  
|**/ Dołącz: {identyfikator PID&#124;ProcessName} [, PID&#124;ProcessName]...**|Zbiera dane z określonych procesów.<br /><br /> Użyj Menedżera zadań, aby wyświetlić identyfikator procesu (PID) i nazwy działających aplikacji procesu.|  
|**/ file:{ReportName}**|Opcjonalna. Określa plik wyjściowy (zastąpi istniejący plik).<br /><br /> Użyj tylko przy użyciu przełącznika/Package lub / dołączyć.|  
|**/ pause**|Wstrzymaj zbieranie danych.|  
|**/Resume**|Wznów zbieranie danych.|  
|**/ stop**|Zatrzymaj zbieranie danych, a następnie Zakończ działanie procesów docelowych.|  
|**/ Odłącz**|Zatrzymaj zbieranie danych, ale pozwól procesów docelowych, które będą nadal działać.|  
|**status**|Pokaż stan profilera.|  
  
## <a name="see-also"></a>Zobacz także  
 [Narzędzia do oceny wydajności w aplikacjach systemu Windows 8 i Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)   
 [Profilowanie z wiersza polecenia](../profiling/using-the-profiling-tools-from-the-command-line.md)