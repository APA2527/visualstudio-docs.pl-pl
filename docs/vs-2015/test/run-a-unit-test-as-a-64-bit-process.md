---
title: Uruchamianie testu jednostkowego jako procesu 64-bitowego | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.assetid: d23a9ee7-58e3-4e8b-a38c-b2207ea73fea
caps.latest.revision: 27
ms.author: gewarren
manager: douge
ms.openlocfilehash: 32f85c68756368f2b2ee2d5b9a1d842497102f41
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259036"
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>Uruchamianie testu jednostkowego jako procesu 64-bitowego
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

W przypadku komputera 64-bitowego, można uruchomić testy jednostkowe i przechwytywanie informacji o pokryciu kodu jako procesu 64-bitowego.  
  
## <a name="running-a-unit-test-as-a-64-bit-process"></a>Uruchamianie testu jednostkowego jako procesu 64-bitowego  
  
#### <a name="to-run-a-unit-test-as-a-64-bit-process"></a>Do uruchomienia testu jednostkowego jako procesu 64-bitowego  
  
1.  Jeśli kodu lub testy zostały skompilowane dla architektury 32-bitowy/x86, ale chcesz uruchamiać je jako procesu 64-bitowego, należy ponownie skompilować je jako **dowolny Procesor**, lub opcjonalnie **64-bitowych**.  
  
    > [!TIP]
    >  Aby zapewnić maksymalną elastyczność, należy skompilować testowane projekty z **dowolny Procesor** konfiguracji. Następnie można uruchomić zarówno 32- i 64 bitowych agentów. Nie posiada zalet kompilowanie projektów testowych mających **64-bitowych** konfiguracji.  
  
2.  Wybierz z menu programu Visual Studio **testu**, następnie wybierz **ustawienia**, a następnie wybierz **architektury procesora**. Wybierz **x64** do uruchamiania testów jako procesu 64-bitowego.  
  
     \- lub —  
  
     Określ `<TargetPlatform>x64</TargetPlatform>` w pliku .runsettings. Zaletą tej metody jest, że można określić grupy ustawień w różnych plikach i szybkie przełączanie się między różnymi ustawieniami. Ponadto można kopiować ustawienia między rozwiązaniami. Aby uzyskać więcej informacji, zobacz [Konfigurowanie testów jednostkowych przy użyciu pliku runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Uruchamianie testów jednostkowych w Eksploratorze testów](../test/run-unit-tests-with-test-explorer.md)   
 [Testowanie jednostek kodu](../test/unit-test-your-code.md)   
 [Wprowadzanie ustawień testów dla testów programu Visual Studio](http://msdn.microsoft.com/library/0c15317e-80c6-4317-aed3-82b8e15e3901)



