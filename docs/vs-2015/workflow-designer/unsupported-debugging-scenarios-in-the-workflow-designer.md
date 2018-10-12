---
title: Nieobsługiwane scenariusze w Projektancie przepływu pracy debugowania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
caps.latest.revision: 4
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: aece5a71965a1935218027dd97b1b8363a646388
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49184486"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nieobsługiwane scenariusze debugowania w Projektancie przepływu pracy
Projektant przepływu pracy w [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] dodano wiele nowych funkcji, ale nadal istnieje kilka scenariuszy debugowania, które nie obsługuje. Ten dokument wyszczególnia nieobsługiwany projektanta przepływu pracy debugowania scenariuszy.  
  
-   Wykonywanie nie mogą być kontynuowane po kod został zmodyfikowany.  
  
-   Wykonywanie nie mogą być kontynuowane z dowolnego punktu w przepływie pracy (Ustaw dalej).  
  
-   Wykonanie nie może być kontynuowane, aż do osiągnięcia kursora (Uruchom do kursora).  
  
-   Projektanta przepływu pracy nie może służyć do debugowania utworzonych w kodzie bez korzystania z projektanta przepływów pracy.  
  
-   Przepływy pracy utworzone we wcześniejszych wersjach programu [!INCLUDE[wf](../includes/wf-md.md)] nie można debugować w [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] projektanta.  
  
-   Punkty przerwania nie może być zdefiniowana w łączach między działaniami lub <xref:System.Activities.Statements.Flowchart> węzłów.  
  
-   Schowek nie jest dostępne podczas debugowania.  
  
-   Punkty przerwania nie są zachowywane podczas działania są kopiowane lub wklejone.  
  
-   Nie można ustawić punktów przerwania przepływu pracy w oknie stosu wywołań.  
  
-   Podczas tworzenia punktów przerwania w Projektancie **wiersza** i **znak** ustawienia w **nowego punktu przerwania** okna dialogowego nie są używane.  
  
-   Menu okna lub skrót punkt przerwania nie obsługuje następujących kolumn lub opcji dla debugowanie przepływu pracy:  
  
    -   Warunek  
  
    -   Liczba trafień  
  
    -   Gdy trafiony  
  
    -   Funkcja  
  
    -   Dane  
  
    -   Proces  
  
    -   Przejdź do demontażu