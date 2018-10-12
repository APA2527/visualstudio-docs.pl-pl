---
title: Lista dezasemblacji — polecenie | Dokumentacja firmy Microsoft
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
- debug.listdisassembly
helpviewer_keywords:
- Debug.ListDisassembly command
- list disassembly command
ms.assetid: eb363e35-e86a-4121-966f-991210c27e2a
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4cbdc3ee566135fe86301deefe1e8be8db431f9f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49256662"
---
# <a name="list-disassembly-command"></a>Lista dezasemblacji — Polecenie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Rozpoczyna proces debugowania i pozwala określić sposób obsługi błędów.  
  
## <a name="syntax"></a>Składnia  
  
```  
Debug.ListDisassembly [/count:number] [/endaddress:expression]  
[/codebytes:yes|no] [/source:yes|no] [/symbolnames:yes|no]  
[/linenumbers:yes|no]  
```  
  
## <a name="switches"></a>Przełączniki  
 Każdy przełącznik może być wywoływany przy użyciu jego wypełniony formularz lub krótka.  
  
 / count: `number` [i] / c: `number` [i] /length: `number` [i] / l: wyświetlenie `number`  
 Opcjonalna. Liczba instrukcji do wyświetlenia. Wartość domyślna to 8.  
  
 /endaddress: `expression` [i] / e: `expression`  
 Opcjonalna. Adres, w którym można zatrzymać dezasemblacji.  
  
 /codebytes:`yes` &#124; `no` [i] /bytes:`yes` &#124; `no` [i] / b:`yes`&#124;`no`  
 Opcjonalna. Wskazuje, czy mają być wyświetlane bajty kodu. Wartość domyślna to `no`.  
  
 / source:`yes` &#124; `no` [i] / s:`yes`&#124;`no`  
 Opcjonalna. Wskazuje, czy ma być wyświetlany kod źródłowy. Wartość domyślna to `no`.  
  
 /symbolnames:`yes` &#124; `no` [i] /names:`yes` &#124; `no` [i] / n:`yes`&#124;`no`  
 Opcjonalna. Wskazuje, czy mają być wyświetlane nazwy symboli. Wartość domyślna to `yes`.  
  
 [/ linenumbers:`yes`&#124;`no`]  
 Opcjonalna. Umożliwia wyświetlanie numerów wierszy skojarzonych z kodem źródłowym. Przełącznik/Source musi mieć wartość `yes` na używanie przełącznika /linenumbers.  
  
## <a name="example"></a>Przykład  
  
```  
>Debug.ListDisassembly  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Lista stosu wywołań — polecenie](../../ide/reference/list-call-stack-command.md)   
 [Lista wątków — polecenie](../../ide/reference/list-threads-command.md)   
 [Visual Studio — polecenia](../../ide/reference/visual-studio-commands.md)   
 [Okno polecenia](../../ide/reference/command-window.md)   
 [Znajdź/Command — pole](../../ide/find-command-box.md)   
 [Visual Studio — aliasy poleceń](../../ide/reference/visual-studio-command-aliases.md)



