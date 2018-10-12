---
title: Komunikaty o błędach w Projektancie przepływu pracy | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- WFDErrorMessages.UI
- System.Activities.Presentation.ErrorActivity.UI
- System.Activities.Presentation.View.ErrorView.UI
ms.assetid: 4d8bbc2e-34fc-477f-9140-4adfd70c34a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 942cd4846b091e31bc74ab3d45860e2782767079
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49305061"
---
# <a name="error-messages-in-workflow-designer"></a>Komunikaty o błędach w Projektancie przepływu pracy
W tym temacie opisano rodzaje komunikatów o błędach, które można napotkać podczas pracy z [!INCLUDE[wfd1](../includes/wfd1-md.md)].  
  
## <a name="situations-in-which-errors-in-the-workflow-designer-occur"></a>Sytuacje, w których występują błędy w Projektancie przepływu pracy  
 Błędy w [!INCLUDE[wfd2](../includes/wfd2-md.md)] wystąpić w następujących sytuacjach:  
  
1.  Istnieje błąd w wyrażeniu.  
  
2.  Ograniczenia sprawdzania poprawności działania nie zostały spełnione.  
  
3.  Wystąpiły błędy w pliku XAML, które powodują działania nie można załadować.  
  
4.  Wystąpiły błędy w pliku XAML, które powodują nie można załadować przepływu pracy.  
  
 Nieprawidłowa wyrażeń i ograniczeń walidacji niezadowolony nie powodują przepływ pracy, aby kompilacja się nie powieść. Tworzenie przepływu pracy zakończy się powodzeniem, ale <xref:System.Activities.InvalidWorkflowException> jest generowany w czasie wykonywania. Jeśli występują błędy w pliku XAML, kompilacja kończy się niepowodzeniem.  
  
 Wewnątrz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], gdy przepływ pracy jest ładowany, jego błędy są wyświetlane w **lista błędów**. Aby przejść do działania, który jest źródłem błędu, klikaj dwukrotnie poszczególne błędy w **lista błędów**.  
  
### <a name="expression-errors"></a>Wyrażenie błędy  
 Nieprawidłowe wyrażenie jest wskazywane przez czerwone kółko z białym wykrzyknika, obok wyrażenia. Przenosząc kursor myszy nad tą ikoną, wyświetla etykietkę narzędzia, która opisuje przyczynę błędu. Wewnątrz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], kliknij przycisk wyrażenie, aby wyświetlić wiersz, który podkreśla źródła błędu. Kursor Wyświetla linie tekstu etykietki narzędzia, która opisuje przyczynę błędu.  
  
### <a name="activity-validation-errors"></a>Błędy sprawdzania poprawności działania  
 Gdy ograniczenia sprawdzania poprawności działania nie zostały spełnione, w prawym górnym rogu działania pojawi się czerwone kółko z białym wykrzyknika. Przenosząc kursor myszy nad tą ikoną, wyświetla etykietkę narzędzia, która opisuje przyczynę błędu.  
  
### <a name="xaml-load-errors"></a>Błędy ładowania XAML  
 Gdy działanie nie powiodło się ładowanie, zostanie wyświetlone okno z czerwoną, z tekstem "nie można załadować działania z powodu błędów w XAML". Dzieje się tak zazwyczaj, gdy nie można rozpoznać typu działania. Nieprawidłowe działanie można usunąć w projektancie, wybierając czerwoną otoczkę i usunięcie go.  
  
### <a name="workflow-load-errors"></a>Błędy ładowania przepływu pracy  
 Gdy przepływ pracy nie można załadować, tekst "Projektanta przepływów pracy napotkał problemy z dokumentu" pojawia się na powierzchni projektowej oraz informacje o wyjątku, który spowodował awarię przepływu pracy do załadowania. Dzieje się tak zazwyczaj, gdy nie można przeanalizować pliku XAML.