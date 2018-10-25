---
title: 'Porady: ochrona programu Outlook przed wyświetlaniem regionów formularzy'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1ec9f45b2055a7a56e067440d216482877da14c2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949061"
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>Porady: ochrona programu Outlook przed wyświetlaniem regionów formularzy
  Może to być sytuacje, w których nie ma programu Microsoft Office Outlook do wyświetlania regionu formularza dla określonego elementu. Na przykład skontaktuj się z pomocą element zawiera adres służbowy, może uniemożliwić pokazujący lokalizacji firmy na mapie wyświetlaniu regionu formularza.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Aby zapobiec wyświetlaniu regionu formularza programu Outlook  
  
1. Otwórz plik kodu dla regionu formularza, który chcesz zmodyfikować.  
  
2. Rozwiń **fabryka regionów formularza** kodu regionu.  
  
3. Dodaj kod, aby `FormRegionInitializing` programu obsługi zdarzeń, która ustawia <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> właściwość <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> klasy **true**.  
  
   W tym przykładzie, jeśli element kontaktu nie zawierają adresu <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> właściwość jest ustawiona na **true**, i regionu formularza nie jest wyświetlana.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>Zobacz także  
 [Tworzenie regionów formularzy programu Outlook](../vsto/creating-outlook-form-regions.md)   
 [Wskazówki: Projektowanie regionów formularzy programu Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Porady: dodawanie regionu formularza do projektu dodatku programu Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Wskazówki: Projektowanie regionów formularzy programu Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Wskazówki: Importowanie regionów formularzy zaprojektowanych w programie Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  