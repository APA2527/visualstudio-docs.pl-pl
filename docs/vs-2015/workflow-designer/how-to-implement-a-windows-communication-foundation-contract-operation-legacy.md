---
title: 'Porady: Implementowanie Windows Communication Foundation operacji kontraktu usługi WCF (starsza wersja) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: d6aeb20e-fac8-4a9d-bd26-ae78bef96b41
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 97e6e72a7de4a9da7dc5086a2fecaea2b378b553
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49264163"
---
# <a name="how-to-implement-a-windows-communication-foundation-contract-operation-legacy"></a>Porady: Implementowanie Windows Communication Foundation operacji kontraktu usługi WCF (starsza wersja)
W tym temacie opisano sposób implementacji [!INCLUDE[indigo1](../includes/indigo1-md.md)] kontrakt operacji za pomocą starszego [!INCLUDE[wfd1](../includes/wfd1-md.md)] przeznaczonego [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] lub [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Po przeciągnięciu **działania ReceiveActivity** działania z przybornika do powierzchni projektu przepływu pracy, albo utworzysz nową [!INCLUDE[indigo2](../includes/indigo2-md.md)] kontraktu lub zaimportować istniejący kontrakt i wykonania operacji. Wybierz i/lub utworzyć kontrakt usługi i jego operacji za pośrednictwem [wybierz operację okno dialogowe (starsza wersja)](../workflow-designer/choose-operation-dialog-box-legacy.md).  
  
### <a name="to-implement-a-wcf-contract-operation"></a>Aby zaimplementować operacji kontraktu usługi WCF  
  
1.  Kliknij dwukrotnie **działania ReceiveActivity** działania w Projektancie lub kliknij wielokropek obok pozycji **właściwości ServiceOperationInfo** właściwość **właściwości** okienka.  
  
2.  Wykonaj jedną z następujących czynności:  
  
    -   Kliknij przycisk **dodać umowy** w prawym górnym rogu okna dialogowego. Spowoduje to utworzenie nowego [!INCLUDE[indigo2](../includes/indigo2-md.md)] kontraktu i operacji dla Ciebie.  
  
         —lub—  
  
    -   Kliknij przycisk **importu** w prawym górnym rogu okna dialogowego. [Wyszukaj i wybierz .NET typu, okno dialogowe (starsza wersja)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) zostanie otwarty. Wyszukaj zestaw lub projekt, który zawiera kontrakt, który chcesz. Wybierz umowę, a następnie kliknij przycisk **OK**.  
  
     Po utworzeniu zamówienia lub zaimportowane, możesz dodać nowe operacje umowę utworzone lub importowane. Aby dodać nową operację, wybierz umowę, a następnie kliknij przycisk **operacji dodawania** w prawym górnym rogu okna dialogowego. Po zakończeniu dodawania operacji, przejdź do kroku 3.  
  
3.  Wybierz operację, którą chcesz skojarzyć z **działania ReceiveActivity** działania. Możesz manipulować definicji operacji, zmieniając nazwę, parametry, właściwości i ustawienia uprawnień wykonać operację.  
  
     Aby zmienić nazwę, wpisz nową nazwę w **nazwy operacji** pola tekstowego.  
  
     Kliknij przycisk **parametry** kartę, aby dostęp do parametrów operacji. Możesz zmienić nazwę, typ lub kierunek parametru, a także dodawanie lub usuwanie parametrów operacji.  
  
     Kliknij przycisk **właściwości** kartę, aby uzyskać dostęp do operacji ochrony poziomu i obsługiwanych wiadomości programu exchange funkcji operacji.  
  
     Kliknij przycisk **uprawnienia** kartę, aby określić, grup, które są dozwolone w celu wykonania operacji.  
  
4.  Kliknij przycisk **OK** i **działania ReceiveActivity** działania będzie wyświetlana nazwa operacji do wykonania operacji, który implementuje.  
  
5.  Umieść działań przepływu pracy ma używać do wykonania tej operacji w ramach **działania ReceiveActivity** działania.  
  
## <a name="see-also"></a>Zobacz też  
 [Wybierz operację, okno dialogowe (starsza wersja)](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [Porady: wywoływanie operacji kontraktu usługi WCF (starsza wersja)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Działania przepływu pracy w starszej wersji](../workflow-designer/legacy-workflow-activities.md)