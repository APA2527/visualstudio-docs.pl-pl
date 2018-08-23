---
title: Aktualizowanie interfejsu użytkownika | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user interfaces, updating
- commands, updating UI
ms.assetid: 376e2f56-e7bf-4e62-89f5-3dada84a404b
caps.latest.revision: 42
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c77fa7407c6c271b66104ed6d835bc516a40c288
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681926"
---
# <a name="updating-the-user-interface"></a>Aktualizowanie interfejsu użytkownika
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [aktualizowania interfejsu użytkownika](https://docs.microsoft.com/visualstudio/extensibility/updating-the-user-interface).  
  
Po zaimplementowaniu polecenia można dodać kod, aby zaktualizować interfejs użytkownika ze stanem nowych poleceń.  
  
 W typowej aplikacji Win32 zestaw poleceń może być sondowany stale i stan pojedynczych poleceń, można dostosować zgodnie z ich wyświetlania. Jednak ponieważ [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] powłoki można hostować nieograniczoną liczbę pakietów VSPackage, rozbudowane sondowania może zmniejszyć czas reakcji, szczególnie sondowania różnych zestawów międzyoperacyjnych między kodem zarządzanym i modelu COM.  
  
### <a name="to-update-the-ui"></a>Aby zaktualizować interfejs użytkownika  
  
1.  Wykonaj jedną z następujących czynności:  
  
    -   Wywołaj <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> metody.  
  
         <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> Można uzyskać interfejsu <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> usługi w następujący sposób.  
  
        ```csharp  
        void UpdateUI(Microsoft.VisualStudio.Shell.ServiceProvider sp)  
        {  
            IVsUIShell vsShell = (IVsUIShell)sp.GetService(typeof(IVsUIShell));  
            if (vsShell != null)  
            {  
                int hr = vsShell.UpdateCommandUI(0);  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);  
            }  
        }  
  
        ```  
  
         Jeśli wartość parametru <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> jest różna od zera (`TRUE`), a następnie aktualizacja jest wykonywana synchronicznie i natychmiast. Firma Microsoft zaleca, aby były przekazywane zero (`FALSE`) dla tego parametru zapewnić dobrą wydajność. Jeśli chcesz uniknąć buforowania, zastosuj `DontCache` Flaga podczas tworzenia polecenia w pliku vsct. Niemniej jednak, Użyj flagi ostrożnie lub może zmniejszyć wydajność. Aby uzyskać więcej informacji na temat flag poleceń, zobacz [Command Flag, Element](../extensibility/command-flag-element.md) dokumentacji.  
  
    -   W pakietach VSPackage, który hostował formantu ActiveX przy użyciu modelu aktywacji w miejscu, w oknie, może być bardziej wygodne do użycia <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> metody. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> Method in Class metoda <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> interfejsu i <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> method in Class metoda <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> interfejsu są funkcjonalnie równoważne. Zarówno spowodować, że do środowiska, aby ponownie Wyślij zapytanie o stan wszystkich poleceń. Zwykle aktualizacja nie jest wykonywane natychmiast. Zamiast tego aktualizacja została opóźniona do czasu bezczynności. Powłoka buforuje stan polecenia, które ułatwiają utrzymanie dobrej wydajności. Jeśli chcesz uniknąć buforowania, zastosuj `DontCache` Flaga podczas tworzenia polecenia w pliku vsct. Niemniej jednak ostrożnie użyć flagi, ponieważ może zmniejszyć wydajność.  
  
         Należy zauważyć, że można uzyskać <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> interfejsu, wywołując `QueryInterface` metody <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager> obiektu lub uzyskania przez interfejs z <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> usługi.  
  
## <a name="see-also"></a>Zobacz też  
 [Jak dodać elementy interfejsu użytkownika w pakietach VSPackage](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Implementacja](../extensibility/internals/command-implementation.md)

