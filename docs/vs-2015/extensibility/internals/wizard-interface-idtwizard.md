---
title: Interfejs kreatora (IDTWizard) | Dokumentacja firmy Microsoft
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
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 28f50dc747e04e909644a6b74f2f4af0d7551248
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266864"
---
# <a name="wizard-interface-idtwizard"></a>Interfejs kreatora (IDTWizard)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Używa zintegrowanego środowiska programistycznego (IDE) <xref:EnvDTE.IDTWizard> interfejs do komunikacji za pomocą kreatorów. Kreatorzy musi implementować ten interfejs, aby mogło zostać zainstalowane w środowisku IDE.  
  
 <xref:EnvDTE.IDTWizard.Execute%2A> Metody jest jedyną metodą, które są skojarzone z <xref:EnvDTE.IDTWizard> interfejsu. Kreatorzy zaimplementować tę metodę i IDE wywołuje metodę w interfejsie. Poniższy przykład pokazuje podpis metody.  
  
```  
/* IDTWizard Method */  
STDMETHOD(Execute)(THIS_  
   /* [in] */ IDispatch *Application,  
   /* [in] */ long hwndOwner,  
   /* [in] */ SAFEARRAY * *ContextParams,  
   /* [in] */ SAFEARRAY * *CustomParams,  
   /* [out] [in] */ wizardResult *RetVal  
   );  
```  
  
 Mechanizm rozpoczęcia jest podobny dla obu **nowy projekt** i **Dodaj nowy element**kreatorów. Aby rozpocząć, albo, należy wywołać <xref:EnvDTE.IDTWizard> interfejsem zdefiniowanym w Dteinternal.h. Jedyna różnica polega na zestaw kontekstu i parametry niestandardowe, które są przekazywane do interfejsu, po wywołaniu interfejsu.  
  
 Poniższe informacje zawierają opis <xref:EnvDTE.IDTWizard> interfejs, który musi implementować kreatorów, aby pracować w [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE. Wywołania środowiska IDE <xref:EnvDTE.IDTWizard.Execute%2A> kreatora, podając mu następujące metody:  
  
-   Obiekt DTE  
  
     Obiekt DTE jest głównym modelu automatyzacji.  
  
-   Dojście do pokazanego poniżej segment kodu, okno dialogowe `hwndOwner ([in] long)`.  
  
     Kreator używa to `hwndOwner` jako element nadrzędny dla okna dialogowego kreatora.  
  
-   Kontekst parametry przekazywane do interfejsu jako wariant dla SAFEARRAY zgodnie z informacjami w segmencie kodu `[in] SAFEARRAY (VARIANT)* ContextParams`.  
  
     Parametry kontekstu zawierać tablicę wartości, które są specyficzne dla rodzaju uruchomieniu kreatora i bieżącego stanu projektu. IDE przekazuje parametrów kontekstu do kreatora. Aby uzyskać więcej informacji, zobacz [parametrów kontekstu](../../extensibility/internals/context-parameters.md).  
  
-   Niestandardowe parametry przekazywane do interfejsu jako wariant dla SAFEARRAY zgodnie z informacjami w segmencie kodu `[in] SAFEARRAY (VARIANT)* CustomParams`.  
  
     Parametry niestandardowe zawierać tablicę parametrów zdefiniowanych przez użytkownika. Plik .vsz przekazuje parametry niestandardowe do środowiska IDE. Wartości są określane przez `Param=` instrukcji. Aby uzyskać więcej informacji, zobacz [parametry niestandardowe](../../extensibility/internals/custom-parameters.md).  
  
-   Są zwracane wartości dla interfejsu  
  
    ```  
    wizardResultSuccess = -1,  
    wizardResultFailure = 0  
    wizardResultCancel = 1  
    wizardResultBackout = 2  
    ```  
  
## <a name="see-also"></a>Zobacz też  
 [Parametry kontekstu](../../extensibility/internals/context-parameters.md)   
 [Parametry niestandardowe](../../extensibility/internals/custom-parameters.md)   
 [Kreatorzy](../../extensibility/internals/wizards.md)   
 [Kreator (plik Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)

