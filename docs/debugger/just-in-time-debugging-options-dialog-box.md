---
title: Just-In-Time, debugowanie, okno dialogowe Opcje | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Debugger.JIT
- vs.debug.options.JIT
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Just-In-Time debugging, setting options
- Options dialog box, debugging
ms.assetid: 7f11b2e3-3fb5-449d-b07c-6ecf1d6a487d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a6736e0646193754dbd932e5501a6473ee18c7e6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936332"
---
# <a name="just-in-time-debugging-options-dialog-box"></a>Just-in-time, debugowanie, opcje ― Okno dialogowe
Aby uzyskać dostęp do **Just-In-Time** strony, przejdź do **narzędzia** menu i kliknij przycisk **opcje**. W **opcje** okna dialogowego rozwiń **debugowanie** a następnie wybierz węzeł **Just-In-Time**. Ta strona umożliwia włączenie debugowania dla kodu zarządzanego, natywnego kodu i skryptów Just-In-Time. Aby uzyskać więcej informacji, zobacz [debugowanie just in Time](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Aby umożliwić debugowanie dla tych typów programów Just-In-Time:  
  
- Zarządzane  
  
- Natywne  
  
- skrypt  
  
  Debugowanie Just In Time jest techniką debugowanie programu, który jest uruchamiany poza [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Można uruchomić programu, który został utworzony w [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] poza [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] środowiska. Włączenie debugowania Just-in-time awarii wyświetli okno dialogowe z pytaniem, jeśli chcesz debugować.  
  
## <a name="associated-warnings"></a>Skojarzone ostrzeżenia  
 Podczas odwiedzania ta strona **opcje** okno dialogowe może pojawić się komunikat ostrzegawczy, następująco:  
  
 **Inny debuger zarejestrował się jako Just-In-Time debugera. Aby naprawić, należy włączyć Just-In-Time debugging lub uruchomić naprawę programu Visual Studio.**  
  
 Ten komunikat występuje, gdy inny debuger, prawdopodobnie starszą wersję [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] debugera, Ustaw jako Just-In-Time debugera.  
  
 Inny komunikat, który może zostać wyświetlony jest następująca:  
  
 **Just In Time wykryto debugowania błędy rejestracji. Aby naprawić, należy włączyć Just-In-Time debugging lub uruchomić naprawę programu Visual Studio.**  
  
 Jeśli zostanie wyświetlony jeden z tych ostrzeżeń debugowanie Just In Time [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] wymaga uprawnień administratora, dopóki problem został rozwiązany. Jeśli zostanie podjęta próba włączenia po prostu — jako bez uprawnień administratora w tych warunkach, zobaczą następujący komunikat o błędzie:  
  
 **Odmowa dostępu. Ma administrator włączyć Just-In-Time debugowanie lub napraw instalację programu Visual Studio.**  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie, opcje ― Okno dialogowe](../debugger/debugging-options-dialog-box.md)   
 [Instrukcje: określanie ustawień debugera](../debugger/how-to-specify-debugger-settings.md)