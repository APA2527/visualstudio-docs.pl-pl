---
title: Upewnij się, że serwer DNS jest prawidłowo skonfigurowany na komputerze docelowym | Microsoft Docs
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.callback_dns_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: cc16217b20d08e9ad2d3b43d3b074652fdffec95
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99871685"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Błąd: upewnij się, że DNS jest prawidłowo skonfigurowany na komputerze docelowym
Podczas próby debugowania zdalnego może zostać wyświetlony następujący komunikat o błędzie:

```cmd
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.
```

 Ten błąd występuje, gdy komputer docelowy nie może rozpoznać nazwy komputera hosta debugera programu Visual Studio. Sprawdź ustawienia DNS na komputerze docelowym.

- Aby uzyskać informacje o wyświetlaniu ustawienia DNS w Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 lub Windows Server 2008 R2, wykonaj następujące czynności: w menu **Start** wybierz polecenie **Pomoc i obsługa techniczna**, a następnie wyszukaj pozycję **Zmień ustawienia protokołu TCP/IP**.

- Aby uzyskać więcej informacji, przejdź do [witryny sieci Web systemu Microsoft Windows](https://www.microsoft.com/windows/) i Wyszukaj pozycję **Zmień ustawienia protokołu TCP/IP**.

  Jeśli nie możesz rozwiązać problemu z usługą DNS, możesz spróbować uruchomić zdalny debuger przy użyciu innego konta. Ten błąd występuje tylko w przypadku uruchamiania zdalnego debugera w ramach konta System lokalny lub usługa sieciowa. W przypadku uruchomienia zdalnego debugera w ramach innego konta może on korzystać z uwierzytelniania NTLM, które nie wymaga usługi DNS. . Aby uzyskać procedurę, zobacz [błąd: usługa zdalny debuger programu Visual Studio na komputerze docelowym nie może nawiązać połączenia z powrotem z tym komputerem](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).
