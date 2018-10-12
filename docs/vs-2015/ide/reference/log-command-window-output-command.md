---
title: Polecenie wyjściowe okna polecenia dziennika | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c48c61177f80be00532347d3c49173aae54c7109
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266399"
---
# <a name="log-command-window-output-command"></a>Zapisuj dane wyjściowe okna Polecenie — Polecenie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Kopiuje wszystkie wejścia i wyjścia z **polecenia** okna w pliku.  
  
## <a name="syntax"></a>Składnia  
  
```  
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]  
```  
  
## <a name="arguments"></a>Argumenty  
 `filename`  
 Opcjonalna. Nazwa pliku dziennika. Domyślnie plik jest tworzony w folderze profilu użytkownika. Jeśli nazwa pliku już istnieje, dziennik jest dołączany na końcu istniejącego pliku. Jeśli plik nie zostanie określony, ostatni określony plik jest używany. Jeśli nie poprzedni plik istnieje, utworzona jest domyślny plik dziennika o nazwie cmdline.log.  
  
> [!TIP]
>  Aby zmienić lokalizację, w której zostanie zapisany plik dziennika, należy wprowadzić pełną ścieżkę pliku ujęta w cudzysłów, jeżeli ścieżka zawiera spacje.  
  
## <a name="switches"></a>Przełączniki  
 Opcja /on  
 Opcjonalna. Rozpoczyna się w dzienniku **polecenia** okna w określonym pliku i dołącza plik o nowe informacje.  
  
 / off  
 Opcjonalna. Zatrzymuje się w dzienniku **polecenia** okna.  
  
 / overwrite  
 Opcjonalna. Jeżeli plik określony w `filename` argumentów pasuje do istniejącego pliku, plik jest zastępowany.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli plik nie zostanie określony, domyślnie jest tworzone cmdline.log pliku. Domyślnie alias dla tego polecenia jest dziennika.  
  
## <a name="examples"></a>Przykłady  
 W tym przykładzie tworzy nowy plik dziennika cmdlog i rozpoczyna się w dzienniku polecenia.  
  
```  
>Tools.LogCommandWindowOutput cmdlog  
```  
  
 W tym przykładzie zatrzymuje rejestrowanie poleceń.  
  
```  
>Tools.LogCommandWindowOutput /off  
```  
  
 W tym przykładzie wznawia rejestrowanie poleceń w pliku dziennika stosowanych wcześniej.  
  
```  
>Tools.LogCommandWindowOutput /on  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Visual Studio — polecenia](../../ide/reference/visual-studio-commands.md)   
 [Okno polecenia](../../ide/reference/command-window.md)   
 [Znajdź/Command — pole](../../ide/find-command-box.md)   
 [Visual Studio — aliasy poleceń](../../ide/reference/visual-studio-command-aliases.md)



