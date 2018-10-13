---
title: Edytuj i Kontynuuj — okno dialogowe komunikat o błędzie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.ENC.SupportedButNotAvaiable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b6252fbaf67a9a5b4173c0fee3f65607e9cc462
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49227243"
---
# <a name="edit-and-continue-error-message-dialog-box"></a>Komunikat o błędzie Edytuj i kontynuuj — Okno dialogowe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

To okno dialogowe pojawia się podczas debugowania w języku, który obsługuje Edit and Continue, ale **Edytuj i Kontynuuj** nie jest dostępna tylko dla typu zmiany kodu, które zostały wprowadzone. Komunikat o błędzie wewnątrz pola zapewnia bardziej szczegółowy opis. Możliwe przyczyny wyświetlania tego okna dialogowego obejmują:  
  
-   Próbowano edytować kodu zarządzanego, gdy debugowanie niezarządzane została włączona. Edytuj i Kontynuuj nie działa w debugowaniu trybu mieszanego.  
  
-   Podjęto próbę edytowania kodu programu SQL Server.  
  
-   Podjęto próbę edytowania kodu podczas debugowania odzyskiwania po awarii. Zrzut programu Watson.  
  
-   Próbowano edytować kod po Wystąpił nieobsługiwany wyjątek i opcji "**Unwind na stosie wywołań dotycząca nieobsłużonych wyjątków**" nie został wybrany.  
  
-   Podjęto próbę edytowania kodu podczas debugowania aplikacji osadzonego środowiska uruchomieniowego.  
  
-   Próbowano edytować kodu w programie, który został załączony do zamiast od **debugowania** menu.  
  
-   Próbowano edytować zoptymalizowanego kodu.  
  
-   Próbowano edytować kodu zarządzanego, gdy obiektem docelowym jest aplikacją 64-bitową. Jeśli chcesz Użyj funkcji Edytuj i Kontynuuj, należy ustawić element docelowy x86. (*Projektu* **właściwości**, **skompilować** karcie **zaawansowane kompilatora** ustawienie.).  
  
-   Próbowano edytować kod w zestawie, który został zmodyfikowany podczas debugowania i został załadowany ponownie.  
  
-   Próbowano edytować kod w zestawie, który nie został załadowany.  
  
-   Rozpoczęto profilowanie starą wersję aplikacji (ponieważ jest to nowa wersja ma błędy kompilacji).  
  
-   Podjęto próbę edytowania kodu została uruchomiona.  
  
## <a name="uielement-list"></a>Lista elementów UI  
 **OK**  
 Zamknij okno dialogowe i Anuluj bezpośrednio poprzednie próby edycji.  
  
## <a name="see-also"></a>Zobacz też  
 [Obsługiwane zmiany kodu (C++)](../debugger/supported-code-changes-cpp.md)



