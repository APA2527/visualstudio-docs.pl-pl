---
title: Debugowanie w trybie mieszanym dla procesów x64 jest obsługiwane tylko w przypadku korzystania z programu Microsoft .NET Framework 4 lub nowszej wersji
description: .NET Framework wersje wcześniejsze niż 4 nie zapewniają obsługi debugowania w trybie mieszanym dla procesów x64. Zapoznaj się z tym artykułem.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 92ec1022842e44f9f87069c48d4de3259dcf8e99
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99913194"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>Debugowanie w trybie mieszanym dla procesów x64 jest obsługiwane tylko w przypadku korzystania z programu Microsoft .NET Framework 4 lub nowszej wersji
.NET Framework wersje wcześniejsze niż 4 nie zapewniają obsługi debugowania w trybie mieszanym dla procesów x64. Oznacza to, że nie można wykonać kroków z kodu zarządzanego do kodu natywnego lub z kodu natywnego do kodu zarządzanego podczas debugowania.

### <a name="workarounds"></a>Obejścia

- Zaktualizuj projekt, tak aby używał Microsoft .NET Framework 4 lub nowszego.

     -lub-

     Debuguj kod zarządzany i natywny w oddzielnych sesjach debugowania.

     -lub-

     Debuguj kod mieszany jako proces 32-bitowy, zgodnie z opisem w poniższych procedurach.

### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Aby zmienić platformę na 32-bitową (Visual Basic lub C#)

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, a następnie kliknij polecenie **Właściwości**.

2. Na stronie właściwości kliknij kartę **kompilacja** lub **Debuguj** .

3. Kliknij pozycję **platforma** i wybierz pozycję x86 z listy platform.

     Domyślnie kompilatory Visual Basic i C# domyślnie tworzą kod do uruchomienia na dowolnym procesorze CPU. Na komputerze 64-bitowym te pliki binarne są uruchamiane jako procesy 64-bitowe. Aby uruchomić program w procesie 32-bitowym, należy wybrać **Win32**, a nie **AnyCPU**.

### <a name="to-change-the-platform-to-32-bit-cc"></a>Aby zmienić platformę na 32-bitową (C/C++)

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, a następnie kliknij polecenie **Właściwości**.

2. Na stronie właściwości kliknij pozycję **platforma** , a następnie wybierz pozycję Win32 z listy platform.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zobacz [Konfigurowanie debugowania SQL](/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100)).

## <a name="see-also"></a>Zobacz też
- [Debuguj 64-bitowe aplikacje](../debugger/debug-64-bit-applications.md)