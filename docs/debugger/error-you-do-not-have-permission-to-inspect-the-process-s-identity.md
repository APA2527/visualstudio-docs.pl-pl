---
title: Nie masz uprawnień do sprawdzenia &apos; tożsamości procesu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: error-reference
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
ms.openlocfilehash: 6903cba8d048d5ed2969d5aa7436fc6eca17561e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99870810"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Błąd: nie masz uprawnień do sprawdzania tożsamości procesu&#39;s
Nie masz uprawnień do sprawdzenia tożsamości procesu. Może to być spowodowane konfiguracją systemu.

 Debuger nie mógł sprawdzić tożsamości procesu, która jest niezbędna do debugowania. Najbardziej prawdopodobną przyczyną jest wyłączenie usług terminalowych. Usługi terminalowe są domyślnie włączone. Wykonaj następujące kroki, aby je ponownie włączyć.

### <a name="to-enable-terminal-services"></a>Aby włączyć usługi terminalowe

1. Kliknij przycisk **Start** , a następnie wybierz pozycję **Panel sterowania**.

2. W panelu sterowania wybierz opcję **Przełącz do widoku klasycznego**, w razie potrzeby, a następnie kliknij dwukrotnie ikonę **Narzędzia administracyjne**.

3. W oknie **Narzędzia administracyjne** kliknij dwukrotnie pozycję **Zarządzanie komputerem**.

4. W oknie Zarządzanie komputerem rozwiń węzeł **usługi i aplikacje** .

5. W obszarze **usługi i aplikacje** kliknij pozycję **usługi**.

     W okienku po prawej stronie zostanie wyświetlona lista usług.

6. Na liście **usługi** kliknij prawym przyciskiem myszy pozycję **usługi terminalowe** , a następnie wybierz polecenie **Właściwości**.

7. W oknie **właściwości usług terminalowych** przejdź do karty **Ogólne** i ustaw **Typ uruchamiania** na **ręczny**.

8. Kliknij przycisk **OK**.

9. Uruchom ponownie komputer.

     Ta procedura nie włącza automatycznie Pulpit zdalny. Jeśli chcesz włączyć Pulpit zdalny na komputerze, wykonaj poniższą procedurę.

### <a name="to-enable-remote-desktop"></a>Aby włączyć Pulpit zdalny

1. Kliknij przycisk **Start** , a następnie kliknij prawym przyciskiem myszy pozycję **mój komputer**.

2. Wybierz pozycję **Właściwości**.

     Zostanie wyświetlone okno **Właściwości systemu** .

3. Kliknij pozycję **zdalne**.

4. W obszarze **pulpit zdalny** wybierz opcję **zezwól użytkownikom na zdalne nawiązywanie połączenia z tym komputerem**.

5. Kliknij przycisk **OK**.

## <a name="see-also"></a>Zobacz też
- [Błędy debugowania zdalnego i rozwiązywanie problemów](../debugger/remote-debugging-errors-and-troubleshooting.md)