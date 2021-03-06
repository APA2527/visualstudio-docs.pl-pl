---
title: Dowiedz się, czy moje wskaźniki uszkadzają adres pamięci | Microsoft Docs
Description: Aby określić, czy wskaźnik powoduje uszkodzenie pamięci, można wyszukać uszkodzenie sterty i można ustawić punkt przerwania danych, aby dowiedzieć się, w jaki sposób wartość jest modyfikowana.
ms.custom: SEO-VS-2020, seodec18
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 3a1857d349f339a537748f11154b43f7d30c7bdb
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99910037"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Jak można sprawdzić, czy wskaźniki uszkadzają adresy pamięci?
## <a name="problem-description"></a>Opis problemu
 Myślę, że jeden ze wskaźników może spowodować uszkodzenie pamięci pod adresem 0x00408000. Jak mogę się dowiedzieć, co się dzieje?

## <a name="solution"></a>Rozwiązanie

#### <a name="check-for-heap-corruption"></a>Sprawdź uszkodzenie sterty

- Większość uszkodzeń pamięci jest w rzeczywistości spowodowana uszkodzeniem sterty. Spróbuj użyć narzędzia globalnych flags (gflags.exe) lub pageheap.exe. Zobacz [/Windows-Hardware/Drivers/Debugger/GFlags-and-Pageheap](/windows-hardware/drivers/debugger/gflags-and-pageheap).

#### <a name="to-find-where-the-memory-address-is-modified"></a>Aby znaleźć miejsce modyfikacji adresu pamięci

1. Ustaw punkt przerwania danych w 0x00408000. Zobacz [Ustawianie punktu przerwania zmiany danych (tylko natywne C++)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus).

2. Po trafieniu punktu przerwania Użyj okna **pamięci** , aby wyświetlić zawartość pamięci, zaczynając od 0x00408000. Aby uzyskać więcej informacji, zobacz [pamięć systemu Windows](../debugger/memory-windows.md).

## <a name="see-also"></a>Zobacz też
- [Debugowanie często zadawanych pytań dotyczących kodu natywnego](../debugger/debugging-native-code-faqs.md)
- [Debugowanie kodu natywnego](../debugger/debugging-native-code.md)
