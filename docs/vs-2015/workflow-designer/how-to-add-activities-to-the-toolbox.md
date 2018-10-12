---
title: 'Porady: dodawanie działań do przybornika | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: b3a8a785-5928-457a-8a50-30267e29503d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 7fc523cd032863498cdefac1e12f0653a57ab7cc
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49299861"
---
# <a name="how-to-add-activities-to-the-toolbox"></a>Porady: dodawanie działań do przybornika
Działania mogą być dodawane do **przybornika** w rozwiązaniu na kilka różnych sposobów. Możesz dodać je z w obrębie bieżącego projektu, odwoływać się do nich z innego projektu lub odwoływać się do nich z innego zestawu.  
  
### <a name="to-add-an-activity-from-within-your-current-project"></a>Aby dodać działanie z w obrębie bieżącego projektu  
  
1.  Dodaj nowe niestandardowe działanie bieżącego projektu przepływu pracy. [!INCLUDE[crabout](../includes/crabout-md.md)] Dodawanie nowego niestandardowego działania do projektu, zobacz [porady: Dodawanie nowego elementu do projektu przepływu pracy](../workflow-designer/how-to-add-a-new-item-to-a-workflow-project.md).  
  
2.  Dodawanie logiki niestandardowej do działania.  
  
3.  Skompiluj projekt. Jeśli kompilacja zakończyła się pomyślnie, Nowa kategoria **przybornika** o nazwie "\<*Nazwa projektu*>" jest wyświetlana przy użyciu niestandardowego działania zawarte w tej kategorii.  
  
    > [!NOTE]
    >  W przypadku zresetowania przybornika działań niestandardowych zostaną usunięte, nawet wtedy, gdy rozwiązanie jest stworzone ponownie. Ponowne wypełnienie przybornika działań niestandardowych po został zresetowany, uruchom ponownie [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
    > [!NOTE]
    >  Przybornik można wyświetlić tylko jednego działania imię. Jeśli dwa działania z różnych zestawów mają taką samą nazwę klasy, zostanie wyświetlona tylko jedna.  
  
    > [!NOTE]
    >  Domeny aplikacji jest współużytkowana przez Edytor wystąpień; Jeśli używane są statyczne zmienne, ich będzie współdzielona przez także wystąpienia edytora. Jeśli nie jest to zachowanie usługi powinny służyć do śledzenia zmiennej wystąpień. Zobacz [przy użyciu tego kontekstu do edycji elementu modelu](http://msdn.microsoft.com/library/7f9f1ea5-0147-4079-8eca-be94f00d3aa1) informacji na temat korzystania z usług w projektancie.  
  
### <a name="to-add-an-activity-from-within-a-different-project"></a>Aby dodać działania z innego projektu  
  
1.  Otwórz rozwiązanie, które zawiera co najmniej jeden projekt przepływu pracy i działania niestandardowego projektu biblioteki lub innego projektu przepływu pracy, który definiuje niestandardowe działanie.  
  
2.  Twórz oba projekty. Jeśli kompilacje zakończyły się pomyślnie Nowa kategoria **przybornika** o nazwie "\<*Nazwa projektu*>" jest wyświetlana przy użyciu niestandardowego działania zawarte w tej kategorii.  
  
### <a name="to-add-an-activity-to-the-toolbox-from-an-assembly"></a>Aby dodać działanie do przybornika z zestawu  
  
1.  Otwórz rozwiązanie, przepływ pracy.  
  
2.  Z **narzędzia** menu, wybierz opcję **wybierz elementy przybornika...** .  
  
3.  W **wybierz elementy przybornika** okno dialogowe, wybierz opcję **karty składniki elementu System.Activities** kartę, a następnie kliknij przycisk **Przeglądaj...** Aby przejść do zestawu, który zawiera niestandardowe działanie, które chcesz dodać.  
  
4.  Wybierz zestaw, a następnie kliknij przycisk **OK**. Składnik niestandardowe działanie zostanie dodany do listy składników i to opcja wybrana automatycznie.  
  
    1.  Kliknij przycisk **OK** aby zamknąć okno dialogowe.  
  
5.  Aby wyświetlić przybornik, wybierz pozycję **przybornika** z **widoku** menu.  
  
6.  Niestandardowe działanie jest wyświetlana w **przybornika** kategorii, która była w trybie koncentracji uwagi, zanim element został dodany. Na przykład jeśli **ogólne** kategorii zostało wybrane w **przybornika** przed dodaniem elementu przybornika, działanie pojawiło się w obszarze **ogólne** kategorii.  
  
## <a name="see-also"></a>Zobacz też  
 [Używanie projektanta przepływu pracy](../workflow-designer/using-the-workflow-designer.md)