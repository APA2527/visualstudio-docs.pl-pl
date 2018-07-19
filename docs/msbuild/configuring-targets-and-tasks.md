---
title: Konfigurowanie obiektów docelowych i zadań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 114e63d1d54f67f15215d17724962b191074588f
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2018
ms.locfileid: "37946554"
---
# <a name="configure-targets-and-tasks"></a>Konfigurowanie obiektów docelowych i zadań
Można skonfigurować elementów docelowych MSBuild oraz zadań do wykonania poza procesem za pomocą narzędzia MSBuild, dzięki czemu możliwe jest określanie kontekstach, które różnią się od jednego są uruchomione na. Na przykład mogą kierować 32-bitowej aplikacji .NET Framework 2.0, jest uruchomiona na komputerze deweloperskim w 64-bitowym systemie operacyjnym .NET Framework 4.5. Można również przeznaczać komputerów, które korzystają z programu .NET Framework 4 lub wcześniej. Kombinacja 32 - lub 64-bitowych i określonej wersji środowiska .NET Framework jest znany jako *kontekstu docelowej*.  
  
## <a name="installation"></a>Instalacja  
 .NET Framework 4.5 i 4.5.1 środowisko uruchomieniowe języka wspólnego (CLR), cele, zadania i narzędzia programu .NET Framework 4 należy zastąpić bez zmieniając ich nazwy. .NET Framework 4.5.1 jest instalowany jako część [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)].  
  
 Jeśli chcesz zainstalować program MSBuild, niezależnie od programu Visual Studio, możesz pobrać pakiet instalacyjny z [pobierania MSBuild](http://go.microsoft.com/fwlink/?LinkId=309745). Należy również zainstalować wersje programu .NET Framework, którego chcesz użyć.  
  
## <a name="targets-and-tasks"></a>Elementy docelowe i zadania  
 Program MSBuild uruchomień niektórych kompilacji zadania poza procesem pod kątem większy zbiór kontekstów.  Na przykład 32-bitowej platformy MSBuild może uruchomić zadania kompilacji w procesie 64-bitowym, 64-bitowy komputer docelowy. Jest to kontrolowane przez `UsingTask` argumentów i `Task` parametrów. Ustaw cele instalowane przez .NET Framework 4.5, tych argumentów i parametrów, a żadne zmiany nie są wymagane do kompilowania aplikacji dla różnych kontekstach docelowego.  
  
 Można utworzyć kontekstu własną target, należy odpowiednio ustawić tych argumentów i parametrów. Szukaj w .NET Framework 4.5 *Microsoft.Common.targets* pliku i *Microsoft.Common.Tasks* plik przykładów.  Aby uzyskać informacji dotyczących sposobu tworzenia niestandardowego zadania, który może pracować w wielu kontekstach docelowego lub sposób modyfikowania istniejących zadań, zobacz [porady: Konfigurowanie obiektów docelowych i zadań](../msbuild/how-to-configure-targets-and-tasks.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Wielowersyjności kodu w programie](../msbuild/msbuild-multitargeting-overview.md)