---
title: Okno dialogowe Opcje listy zadań, środowisko, | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Environment.Task_List
- VS.ToolsOptionsPag.Environment.Task_List
- VS.ToolsOptionsPages.Environment.TaskList
- VS.Environment.Task List
helpviewer_keywords:
- Token List
- tokens
- icons, in Task List
- Task List, customizing environment
- Options dialog box, Task List environment
- exclamation points
- comments, comment tasks in Task List
- tokens, and the Task List
- Task List, comment tasks
ms.assetid: 88327e04-fa3e-48db-995b-ad89e0dc4ed2
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d96543e5f8cc7d1513f335fc6a54f669dfa5f356
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681092"
---
# <a name="task-list-environment-options-dialog-box"></a>Lista zadań, środowisko, opcje — Okno dialogowe
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [okno dialogowe Opcje listy zadań, środowisko,](https://docs.microsoft.com/visualstudio/ide/reference/task-list-environment-options-dialog-box).  
  
  
Ta strona opcji pozwala na dodawanie, usuwanie i zmienianie tokenami komentarzy, które generują **listy zadań** przypomnienia. Aby wyświetlić te ustawienia, wybierz **opcje** z **narzędzia** menu, rozwiń węzeł **środowiska** folderu i wybierz polecenie **listy zadań**.  
  
## <a name="task-list-options"></a>Opcje listy zadań  
 Potwierdź usunięcie zadania  
 Po wybraniu wyświetlane jest okno wiadomości, zawsze wtedy, gdy zadanie użytkownika są usuwane z **listy zadań**, co pozwala potwierdzić usunięcie. Ta opcja jest domyślnie wybrana.  
  
> [!NOTE]
>  Aby usunąć komentarza do zadania, użyj linku, aby znaleźć komentarz, a następnie usuń go z kodu.  
  
 Pokazuj tylko nazwy plików  
 Po wybraniu **pliku** kolumny **listy zadań** wyświetla tylko nazwy plików, które można edytować, nie ich pełnej ścieżki.  
  
## <a name="tokens"></a>Tokeny  
 Po wstawieniu komentarz w kodzie, którego tekst zaczyna się od tokenu z **lista tokenów**, **listy zadań** Wyświetla komentarz jako nowy wpis, zawsze wtedy, gdy plik jest otwarty do edycji. Możesz kliknąć to **listy zadań** wpis, aby bezpośrednio przejść do wiersza komentarza w kodzie. Aby uzyskać więcej informacji, zobacz [korzystanie z listy zadań](../../ide/using-the-task-list.md).  
  
 lista tokenów  
 Wyświetla listę tokenów i umożliwia dodawanie lub usuwanie tokeny niestandardowe. Tokeny komentarza to wielkości liter w Visual C# i Visual C++, ale nie w języku Visual Basic.  
  
> [!NOTE]
>  Jeśli nie wpiszesz żądanego tokenu dokładnie tak, jak pojawiają się one w **lista tokenów**, komentarz zadania nie będą wyświetlane w **listy zadań**.  
  
 Priorytet  
 Ustawia priorytet zadania korzystające z wybranego tokenu. Komentarze do zadań, które zaczynają się od tego tokenu są automatycznie przypisywane wyznaczonym priorytet w **listy zadań**.  
  
 Nazwa  
 Wprowadź ciąg tokenu. Dzięki temu **Dodaj** przycisku. Na **Dodaj**, te parametry są objęte **lista tokenów**, i komentarze rozpoczynające się od ta nazwa będzie wyświetlana w **listy zadań**.  
  
 Dodaj  
 Włączony podczas wprowadzania nowej **nazwa**. Kliknij, aby dodać nowy ciąg tokenu przy użyciu wartościami podanymi w **nazwa** i **priorytet** pola.  
  
 Usuwanie  
 Kliknij, aby usunąć wybrany token z **lista tokenów**. Nie można usunąć domyślny token komentarz.  
  
 Zmiana  
 Kliknij, aby wprowadzić zmiany do istniejącego tokenu przy użyciu wartościami podanymi w **nazwa** i **priorytet** pola.  
  
> [!NOTE]
>  Nie można zmienić ani usunąć domyślny token komentarz, ale można zmienić jego priorytet.  
  
## <a name="see-also"></a>Zobacz też  
 [Korzystanie z listy zadań](../../ide/using-the-task-list.md)   
 [Ustawianie zakładek w kodzie](../../ide/setting-bookmarks-in-code.md)   
 [Środowisko, Opcje — okno dialogowe](../../ide/reference/environment-options-dialog-box.md)



