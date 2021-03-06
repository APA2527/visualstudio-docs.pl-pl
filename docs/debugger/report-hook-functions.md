---
title: Raportowanie funkcji punktu zaczepienia | Microsoft Docs
description: Przejrzyj funkcje punktu zaczepienia raportu w programie Visual Studio. Funkcja podłączania raportów zainstalowana przy użyciu _CrtSetReportHook jest wywoływana za każdym razem, gdy _CrtDbgReport generuje raport debugowania.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: bb1e6d2fcd3ec5a2e2c1d784724b17298f0b3e84
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99891335"
---
# <a name="report-hook-functions"></a>Raportowanie funkcji punktów zaczepienia
Funkcja podłączania raportów zainstalowana przy użyciu [_CrtSetReportHook](/cpp/c-runtime-library/reference/crtsetreporthook)jest wywoływana za każdym razem, gdy [_CrtDbgReport](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) generuje raport debugowania. Można jej używać między innymi w przypadku filtrowania raportów, aby skoncentrować się na określonych typach alokacji. Funkcja punktu zaczepienia raportu powinna mieć prototyp podobny do następującego:

```cpp
int YourReportHook(int nRptType, char *szMsg, int *retVal);
```

 Wskaźnik przekazany do **_CrtSetReportHook** jest typu **_CRT_REPORT_HOOK**, zgodnie z definicją w CRTDBG. C

```cpp
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);
```

 Gdy Biblioteka wykonawcza wywołuje funkcję Hook, argument *nRptType* zawiera kategorię raportu (**_CRT_WARN**, **_CRT_ERROR** lub **_CRT_ASSERT**), *szMsg* zawiera wskaźnik do w pełni zmontowany ciąg komunikatu raportu, a *retval* określa, czy `_CrtDbgReport` należy kontynuować normalne wykonywanie po wygenerowaniu raportu lub uruchomieniu debugera. (Wartość *retval* zero kontynuuje wykonywanie, A wartość 1 powoduje uruchomienie debugera).

 Jeśli hak przechwytuje komunikat w całości, więc nie jest wymagane żadne dalsze raportowanie, należy zwrócić **wartość true**. Jeśli zwraca **wartość false**, `_CrtDbgReport` będzie zgłaszać komunikat w normalny sposób.

## <a name="see-also"></a>Zobacz też
- [Zapisywanie funkcji punktu zaczepienia debugowania](../debugger/debug-hook-function-writing.md)
- [Przykład crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)
