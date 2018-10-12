---
title: Zdarzenia kompilacji okno dialogowe (Visual Basic) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4d0ad4235a309fafd025c4c205b9fa150f47af5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189101"
---
# <a name="build-events-dialog-box-visual-basic"></a>Zdarzenia kompilacji (Visual Basic) — Okno dialogowe
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Użyj **zdarzenia kompilacji** okno dialogowe, aby określić instrukcje dotyczące konfiguracji kompilacji. Można również określić warunki, w których są uruchamiane wszystkie zdarzenia sprzed kompilacji lub po kompilacji. Aby uzyskać więcej informacji, zobacz [jak: Specify Build Events (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
 **Wiersz polecenia zdarzenia sprzed kompilacji**  
 Określa wszystkie polecenia do wykonania przed rozpoczęciem kompilacji. Do typu long polecenia, kliknij przycisk **Edytuj prekompilacji** do wyświetlenia [prekompilacji zdarzeń/po kompilacji — zdarzenie wiersza polecenia okno dialogowe](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  Jeśli projekt jest aktualny, a nie kompilacja zostaje wyzwolona, nie należy uruchamiać zdarzenia prekompilacyjnego.  
  
 **Wiersz polecenia zdarzenia po kompilacji**  
 Określa wszystkie polecenia do wykonania po zakończeniu kompilacji. Do typu long polecenia, kliknij przycisk **edytować po kompilacji** do wyświetlenia **zdarzeń/po kompilacji — zdarzenia prekompilacyjnego d wiersza polecenia**ialog pole.  
  
> [!NOTE]
>  Dodaj `call` instrukcję przed polecenia wszystkich wykonywanych po kompilacji, które uruchamiają pliki bat. Na przykład `call C:\MyFile.bat` lub `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Uruchom zdarzenie po kompilacji**  
 Określa warunki dla zdarzenia postkompilacyjnego do uruchomienia, jak pokazano w poniższej tabeli.  
  
|Opcja|Wynik|  
|------------|------------|  
|**zawsze**|Zdarzenie po kompilacji zostaną uruchomione, niezależnie od tego, czy kompilacja zakończy się pomyślnie.|  
|**W przypadku pomyślnej kompilacji**|Zdarzenie po kompilacji będzie działać, jeśli kompilacja zakończy się pomyślnie. Zdarzenie uruchomią się nawet w przypadku projektu, który jest aktualne, tak długo, jak kompilacja zakończy się pomyślnie. To jest ustawienie domyślne.|  
|**Gdy kompilacja aktualizuje dane wyjściowe projektu**|Zdarzenie po kompilacji zostanie uruchomiony tylko wtedy, gdy plik wyjściowy kompilatora (.exe lub .dll) różni się od poprzedniego pliku danych wyjściowych kompilatora. Zdarzenie po kompilacji nie zostanie uruchomione, gdy projekt jest aktualny.|  
  
## <a name="see-also"></a>Zobacz też  
 [Strona kompilowania, Projektant projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Porady: Określanie zdarzeń kompilacji (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Wiersz polecenia zdarzenia sprzed kompilacji/zdarzenia po kompilacji, okno dialogowe](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)



