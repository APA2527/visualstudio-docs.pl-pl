---
title: Zapytania Edytuj zapytanie, Zapisz (pakiet VSPackage kontroli) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- QEQS events
- Query Edit Query Save events
- source control packages, Query Edit Query Save events
ms.assetid: c360d2ad-fe42-4d65-899d-d1588cc8a322
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 612bd94ba360f496c08ea25fd1a45e15c88edb6e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49172396"
---
# <a name="query-edit-query-save-source-control-vspackage"></a>Edytowanie i zapisywanie zapytań (pakiet VSPackage kontroli kodu źródłowego)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] edytory może emitować zdarzenia zapytania Edytuj zapytanie Zapisz (QEQS). [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Klasy zastępczej kontroli źródła implementuje usługę QEQS tak, aby odbiorca zdarzenia QEQS. Zdarzenia te są następnie delegowane do kontroli źródła aktualnie aktywnego pakietu VSPackage. Implementuje pakietu VSPackage do kontroli źródła active <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> i jego metod. Metody `IVsQueryEditQuerySave2` interfejsu są zwykle nazywane bezpośrednio przed wykonaniem edycji dokumentu po raz pierwszy, i od razu, aby dokument został zapisany.  
  
## <a name="queryeditquerysave-events"></a>Zdarzenia QueryEditQuerySave  
 Kontrola źródła pakietu VSPackage musi obsługiwać zdarzenia QEQS implementując `IVsQueryEditQuerySave2` interfejsu i niezbędne metody. Poniżej przedstawiono krótki opis pakietu VSPackage musi implementować co najmniej dwóch metod. Rzeczywiste wdrożenie muszą być zgodne z logiką odpowiedni model kontroli źródła.  
  
### <a name="queryeditfiles-method"></a>Metoda QueryEditFiles  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> Jest wywoływana, gdy projekt lub Edytor chce modyfikacji pliku. W idealnym przypadku ta metoda jest wywoływana *przed* plik zostanie zmodyfikowany i przy zapisywaniu pliku. Po wywołaniu, `IVsQueryEditQuerySave2::QueryEditFiles` metoda sprawdza, czy dany pliki znajdują się pod kontrolą źródła, czy muszą zostać wyewidencjonowany i czy można wykorzystać. Jeśli okoliczności uniemożliwić pliki można edytować, `IVsQueryEditQuerySave2::QueryEditFiles` metoda informuje program wywołujący, aby anulować edycję. Jest również możliwe do obiektu wywołującego określić tryb wywołania. W trybie "silent" Ta metoda przyjmuje akcję tylko wtedy, gdy nie powoduje wyświetlenie wszelkich elementów interfejsu użytkownika. Jeśli interfejs użytkownika jest nieuniknione, Flaga musi zostać zwrócona do wskazują na problem.  
  
 Metoda działa w sposób transakcyjny; oznacza to jeśli edycji zostanie anulowana na pojedynczy plik, Edytuj została anulowana, dla wszystkich plików. Z drugiej strony Jeśli edycja jest dozwolone, jest dozwolona dla wszystkich plików. Jeśli ta metoda umożliwia edytowanie raz dla danego zestawu plików, jego musi zawsze Zezwalaj na edycję w kolejnych wywołaniach dla tego samego zestawu plików. Zezwalaj na edytowanie pętli jest powtarzany do momentu pliki są zamknięte, zapisać i ponownie załadować; do momentu zmiany jego atrybutów (właściwości); lub dopóki nie zostanie zmieniony pakietu kontroli źródła. Sytuacjach należy rozważyć Implementowanie `IVsQueryEditQuerySave2::QueryEditFiles` metody obejmują wiele plików, pliki specjalne, Anuluj od użytkownika i edycję w pamięci.  
  
### <a name="querysavefiles-method"></a>Metoda QuerySaveFiles  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> Jest wywoływana, gdy projekt lub Edytor potrzebne do zapisania zestawu plików. Po wywołaniu, `IVsQueryEditQuerySave2::QuerySaveFiles` metoda sprawdza w przypadku danego pliki tylko do odczytu oraz czy są one pod kontrolą źródła. Jeśli pliki muszą zostać wyewidencjonowane, wywołanie jest delegowane do pakietu kontroli źródła. Jeśli okoliczności uniemożliwić pliki są zapisywane, `IVsQueryEditQuerySave2::QuerySaveFiles` metoda musisz poinformować edytora, aby anulować zapisywanie. Podobnie jak w przypadku `IVsQueryEditQuerySave2::QueryEditFiles` metody jest możliwe do obiektu wywołującego określić tryb wywołania. W trybie "silent" Ta metoda przyjmuje akcję tylko wtedy, gdy nie powoduje wyświetlenie wszelkich elementów interfejsu użytkownika. Jeśli interfejs użytkownika jest nieuniknione, Flaga musi zostać zwrócona do wskazują na problem.  
  
 Ta metoda musi zachowywać się w sposób transakcyjny; oznacza to jeśli zapisu została anulowana na pojedynczy plik, Zapisz została anulowana, dla wszystkich plików. Z drugiej strony jeśli jest dozwolone zapisywanie, muszą być dozwolone dla wszystkich plików. Podobnie jak w przypadku `IVsQueryEditQuerySave2::QueryEditFiles` metody, przypadkach należy rozważyć Implementowanie `IVsQueryEditQuerySave2::QuerySaveFiles` metody obejmują wiele plików, pliki specjalne, Anuluj od użytkownika i edycję w pamięci.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>

