---
title: 'Porady: wrócić do funkcji, która wywołała MFC przy zatrzymaniu | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da15793027eb643078771d33464258fea73fec9d
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283395"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Porady: powracanie do funkcji, która wywołała MFC przy zatrzymaniu
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz Importuj i Eksportuj ustawienia w menu Narzędzia. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
 Jeśli użyto **Przerwij** polecenie **debugowania** menu, aby zatrzymać program zakończył w MFC i wiesz, czy problem jest w kodzie okno stosu wywołań można przejść z powrotem do funkcji. Aby uzyskać więcej informacji, zobacz [porady: Korzystanie z okna stosu wywołań](../debugger/how-to-use-the-call-stack-window.md).  
  
 Czasami Twój kod może spowodować przerwanie "pompy komunikatów". W takiej sytuacji istnieje żaden kod użytkownika w stosie wywołań. Aby uniknąć tego problemu, można użyć punktów przerwania (także z warunków i liczniki trafień) zamiast **Przerwij** polecenia. Aby uzyskać więcej informacji, zobacz [punkty przerwania i śledzenia](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>Aby przejść do funkcji, z którego wywołano MFC  
  
-   Użyj **stos wywołań** okna.  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie kodu natywnego — często zadawane pytania](../debugger/debugging-native-code-faqs.md)   
 [Debugowanie kodu natywnego](../debugger/debugging-native-code.md)