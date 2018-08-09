---
title: Obsługa błędów i wartości zwracane | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- errors [Visual Studio SDK], handling
- error handling
- return values
ms.assetid: b2d9079d-39a6-438a-8010-290056694b5c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 128326b869f9a1e09ffb28118af1073b1a7e57b1
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39638635"
---
# <a name="error-handling-and-return-values"></a>Obsługa błędów i zwracanych wartości
Pakietów VSPackage i COM należy użyć takiej samej architekturze błędów. `SetErrorInfo` i `GetErrorInfo` funkcje są częścią interfejsu programowania aplikacji (API) systemu Win32. Dowolnego pakietu VSPackage w zintegrowanym środowisku programistycznym (IDE) można wywołać te globalne interfejsów API systemu Win32 do rekordu szczegółowych informacji o błędach podczas odbierania powiadomienia o błędzie. [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Zawiera zestawy międzyoperacyjne, do zarządzania informacjami o błędzie.  
  
## <a name="interop-methods"></a>Metody międzyoperacyjności  
 Dla wygody, IDE udostępnia metodę, <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>, zamiast wywoływania interfejsów API systemu Win32. Używany kod zarządzany <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>. Gdy błąd `HRESULT` dociera do poziomu, w którym powinien być wyświetlany komunikat o błędzie (często jest to obiekt Implementowanie <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> program obsługi poleceń), IDE używa innej metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A>, aby wyświetlić okno odpowiedni komunikat. Używany kod zarządzany <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> metody.  
  
 Jako implementującego pakietu VSPackage, zwykle zaimplementować obiekty COM `ISupportErrorInfo`. `ISupportErrorInfo` Interfejsu gwarantuje, że szczegółowych informacji o błędach można przenieść w pionie łańcuch wywołań. Obiekty, które mogą być używane w procesy lub w wielu wątkach musi obsługiwać `ISupportErrorInfo` aby upewnić się, że szczegółowych informacji o błędach jest prawidłowo organizowane obiektu wywołującego.  
  
 Wszystkie obiekty, które są związane z pakietami VSPackage i które są zaangażowane w rozszerzanie środowiska IDE, w tym fabryki edytora, edytory, hierarchii oraz oferowanych usług, powinien obsługiwać szczegółowych informacji o błędach. Podczas gdy IDE nie wymagają tych obiektów pakietu VSPackage, aby zaimplementować `ISupportErrorInfo`, zawsze jest zalecane.  
  
 Środowisko IDE jest odpowiedzialny za raportowanie informacji o błędach i wyświetlanie ich do użytkownika [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zawsze wtedy, gdy `HRESULT` jest propagowana do środowiska IDE. Środowisko IDE jest również mechanizm tworzenia `ErrorInfo` obiektów.  
  
## <a name="general-guidelines"></a>Ogólne wskazówki  
 Możesz użyć <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> i <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> metody do ustawiania i raportowania błędów, które są wewnętrzne dla Twojego wdrożenia pakietu VSPackage. Jednak zgodnie z ogólną zasadą, należy przestrzegać następujących wytycznych, do obsługi komunikatów o błędach w swojej pakietu VSPackage:  
  
-   Implementowanie `ISupportErrorInfo` w obiekty COM pakietu VSPackage.  
  
-   Utwórz mechanizm, który wywołuje raportowania błędów <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metody w obiektach, które implementują <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
-   Pozwól IDE, błędy są wyświetlane użytkownikom za pośrednictwem <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> metody.  
  
## <a name="error-information-in-the-ide"></a>Informacje o błędzie w środowisku IDE  
 Następujące reguły określają, jak należy obsługiwać informacje o błędzie w [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE:  
  
-   Jak strategii obrony w celu zagwarantowania, że informacje o błędzie starych nie jest zgłaszany do użytkowników, funkcje to wywołanie <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> najpierw wywołać metodę <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metody. Przekaż `null` wyczyść komunikaty o błędach pamięci podręcznej przed wywołaniem niczego, który może być nowe informacje o błędzie.  
  
-   Funkcje, które nie zgłaszają bezpośrednio komunikaty o błędach są dozwolone tylko w celu wywołania <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metodę, jeśli są one zwróci błąd `HRESULT`. Jest dozwolone, aby wyczyścić `ErrorInfo` przy wejściu do funkcji, lub gdy zwracany jest <xref:Microsoft.VisualStudio.VSConstants.S_OK>. Jedynym wyjątkiem od tej reguły jest po wywołaniu zwraca błąd `HRESULT` z którym otrzymującej można odzyskać jawnie lub zignorować.  
  
-   Każda strona, która jawnie ignoruje błąd `HRESULT` musi wywołać <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metody z <xref:Microsoft.VisualStudio.VSConstants.S_OK>. W przeciwnym razie `ErrorInfo` obiektu może przypadkowo użyty po innej strony generuje błąd bez podawania ich własnych `ErrorInfo`.  
  
-   Wszystkie metody, które pochodzą z błędem `HRESULT` zachęcamy do wywołania <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metodę w celu udostępnienia szczegółowych informacji o błędach. Jeśli zwrócony `HRESULT` jest specjalny `FACILITY_ITF` błąd, a następnie metody, które są wymagane do świadczenia odpowiedniego `ErrorInfo`obiektu. Jeśli zwrócony kod błędu to błąd standardowy system (na przykład <xref:Microsoft.VisualStudio.VSConstants.E_OUTOFMEMORY>, <xref:Microsoft.VisualStudio.VSConstants.E_ABORT>, <xref:Microsoft.VisualStudio.VSConstants.E_INVALIDARG>, <xref:Microsoft.VisualStudio.VSConstants.E_UNEXPECTED>i tak dalej.) jest dopuszczalne zwrócony kod błędu bez jawnego wywołania <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metody. Jako obrony strategii kodowania, gdy błąd pochodzący `HRESULT` (w tym błędy systemowe), zawsze wywołuj <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metoda, za pomocą `ErrorInfo` opisujący błąd bardziej szczegółowo, lub `null`.  
  
-   Wszystkie funkcje, które zwracają błąd zainicjowany przez inne wywołanie musi pomyślnie przejść na informacjach, które zostały odebrane z niepowodzenia wywołania w `HRESULT` bez modyfikowania `ErrorInfo` obiektu.  
  
## <a name="see-also"></a>Zobacz także  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [Seterrorinfo — (Automatyzacja składnika)](http://msdn.microsoft.com/8eaacfac-fc37-4eaa-870b-10b99d598d66)   
 [Geterrorinfo —](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-geterrorinfo)   
 [Interfejs ISupportErrorInfo interfejsu](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo)
