---
title: 'Porady: aktualizowanie pasek stanu | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b7f7d52ad8dc75f8e8bd313794b44c231522cde7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829940"
---
# <a name="how-to-update-the-status-bar"></a>Porady: aktualizowanie paska stanu
**Pasek stanu** pasek sterowania znajduje się w dolnej części wiele okien aplikacji, zawierający co najmniej jeden stan wierszy tekstu lub wskaźniki.  
  
## <a name="to-update-the-status-bar"></a>Aby zaktualizować paska stanu  
  
1.  Implementowanie <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> dla każdego obiektu poszczególnych widoku (DocView), zapewniająca edytora, takie jak widok formularza i widoku kodu.  
  
2.  Kiedy wywołuje IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>, zaktualizuj informacje w **pasek stanu** przez wywołanie metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>.  
  
    > [!NOTE]
    >  Wywołania środowiska IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> tylko kiedy okno dokumentu został początkowo uaktywniony. Pozostały okres czasu, który okna dokumentu jest aktywny, należy zaktualizować **pasek stanu** informacji jako stan zmiany edytora.  
  
## <a name="robust-programming"></a>Skuteczne programowanie  
 A **pasek stanu** zawiera cztery oddzielne pola:  
  
- Tekst statusu  
  
- Pasek postępu  
  
- Animowaną ikonę  
  
- Edytor informacji  
  
  Aby uzyskać więcej informacji, zobacz [paski stanu](/cpp/mfc/status-bars).  
  
  IDE automatycznie wywołuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> metody usługi <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> wdrożenia po uaktywnieniu okna dokumentu.  
  
  Implementujący pakietu VSPackage jest odpowiedzialny za aktualizowanie tekst statusu na pasku stanu. IDE resetuje ten ciąg na "GOTOWY", jeśli pole tekstowe stan jest ustawiony na pusty tekst ("") w czasie bezczynności.  
  
## <a name="see-also"></a>Zobacz także  
 [Paski stanu](/cpp/mfc/status-bars)