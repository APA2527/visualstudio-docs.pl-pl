---
title: 'Porady: Dodawanie nowego elementu do projektu przepływu pracy | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1779fa4f3f644913bfe39164e707dfee4673502b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673753"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Porady: Dodawanie nowego elementu do projektu przepływu pracy
Po utworzeniu projektu przepływu pracy, można dodać działania przepływu pracy, projektantów i innych znanych [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] elementy do projektu.  
  
 W poniższej tabeli wymieniono [!INCLUDE[wf](../includes/wf-md.md)] elementy, które można dodać do projektu przepływu pracy.  
  
|Nazwa|Opis|  
|----------|-----------------|  
|Działanie|Działanie składa się z innymi działaniami. Wybranie tej pozycji dodaje ten sam plik XAML do projektu, jak można uzyskać po wybraniu **Biblioteka działań** szablonu dla nowego projektu. [!INCLUDE[crabout](../includes/crabout-md.md)] Korzystając z tej procedury zobacz [porady: Tworzenie biblioteki działań](../workflow-designer/how-to-create-an-activity-library.md).|  
|Projektant działań|Projektant umożliwiający dostosowanie środowiska czasu projektowania, działania. Wybranie tej pozycji dodaje te same pliki do projektu, jak można uzyskać po wybraniu **Biblioteka projektanta działań** szablonu dla nowego projektu. [!INCLUDE[crabout](../includes/crabout-md.md)] Korzystając z tej procedury zobacz [porady: Tworzenie biblioteki projektanta działań](../workflow-designer/how-to-create-an-activity-designer-library.md).|  
|Działanie kodu|Działanie z logiką wykonywania zapisaną w kodzie. Plik kodu źródłowego za pomocą zastąpienia z <xref:System.Activities.CodeActivity.Execute%2A> metoda została już wygenerowana dla Ciebie.|  
|Usługa przepływu pracy WCF|A [!INCLUDE[indigo2](../includes/indigo2-md.md)] oferująca przy użyciu działań przepływu pracy. Wybranie tej pozycji dodaje te same pliki do projektu, jak można uzyskać po wybraniu **aplikacja usługi przepływu pracy WCF** szablonu dla nowego projektu. [!INCLUDE[crabout](../includes/crabout-md.md)] Korzystając z tej procedury zobacz [porady: tworzenie aplikacji usługi przepływu pracy WCF](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|  
  
### <a name="to-add-a-new-item-to-a-workflow-project"></a>Aby dodać nowy element do projektu przepływu pracy  
  
1.  Na **projektu** menu, kliknij przycisk **Dodaj nowy element...** .  
  
     **Dodaj nowy element** zostanie otwarte okno dialogowe.  
  
2.  W **zainstalowane szablony** okienku wybierz **przepływu pracy** grupy.  
  
3.  Wybierz jedną z czterech elementów. W poprzedniej tabeli wymieniono opcje dostępne do wyboru.  
  
4.  Wpisz odpowiednią nazwę dla elementu w **nazwa** u dołu okna dialogowego.  
  
5.  Kliknij przycisk **Dodaj** Aby dodać element do bieżącego projektu przepływu pracy.  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie projektu przepływu pracy](../workflow-designer/creating-a-workflow-project.md)