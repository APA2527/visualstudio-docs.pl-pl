---
title: 'Porady: Tworzenie niestandardowego tekstu znaczniki | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - custom text markers
ms.assetid: 6e32ed81-c604-4a32-9012-8db3bec7c846
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7ac2ad16c0e6a3e0a6c76e15ff6860838fa349c2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49893107"
---
# <a name="how-to-create-custom-text-markers"></a>Porady: Tworzenie niestandardowego tekstu znaczników
Jeśli chcesz utworzyć znacznika niestandardowego tekstu, aby podkreślić lub organizowanie kodu, należy wykonać następujące czynności:  
  
- Zarejestruj nowy znacznik tekst tak, aby inne narzędzia do niego dostęp.  
  
- Podaj domyślną implementację i konfiguracji znacznika tekstu.  
  
- Tworzenie usługi, która może służyć przez inne procesy, aby użyć znacznika tekstu.  
  
  Szczegółowe informacje na temat sposobu stosowania znacznika tekstu do regionu kodu, [porady: Korzystanie ze znaczników tekstu](../extensibility/how-to-use-text-markers.md).  
  
## <a name="to-register-a-custom-marker"></a>Aby zarejestrować znacznika niestandardowego  
  
1. Utwórz wpis rejestru w następujący sposób:  
  
    **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\\<wersji > Znaczniki \Text Editor\External\\\<MarkerGUID >**  
  
    *\<MarkerGUID >* jest `GUID` używany do identyfikowania znacznika dodawany  
  
    `<Version>` jest wersją [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], na przykład 8.0  
  
    `<PackageGUID>` Identyfikator GUID pakietu VSPackage implementuje obiektu automatyzacji.  
  
   > [!NOTE]
   >  Ścieżka katalogu głównego **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\\<wersji >** może zostać zastąpiona przez główny alternatywne po zainicjowaniu powłoki programu Visual Studio, aby uzyskać więcej informacji, zobacz [Przełączniki wiersza polecenia](../extensibility/command-line-switches-visual-studio-sdk.md).  
  
2. Utwórz cztery wartości w obszarze **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\\<wersji > \Text Editor\External znaczniki\\\<MarkerGUID >**  
  
   -   (Domyślnie)  
  
   -   Usługa  
  
   -   Nazwa wyświetlana  
  
   -   Package  
  
   -   `Default` wpis jest opcjonalny typu REG_SZ. Po ustawieniu wartości wpisu jest ciąg zawierający pewne przydatne informacje identyfikacyjne, na przykład "niestandardowego tekstu znacznika".  
  
   -   `Service` jest wpis typu REG_SZ zawierający ciąg identyfikatora GUID usługi, która zawiera znacznik niestandardowego tekstu przez proffering <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>. Format jest {XXXXXX XXXX XXXX XXXX XXXXXXXXX}.  
  
   -   `DisplayName` to wpis typu REG_SZ zawierający identyfikator zasobu o nazwie znacznika niestandardowego tekstu. Format jest #YYYY.  
  
   -   `Package` wpis typu REG_SZ zawierającego `GUID` pakietu VSPackage, która dostarcza usługę wymienionych w ramach usługi. Format jest {XXXXXX XXXX XXXX XXXX XXXXXXXXX}.  
  
## <a name="to-create-a-custom-text-marker"></a>Aby utworzyć znacznika niestandardowego tekstu  
  
1.  Implementowanie <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> interfejsu.  
  
     Implementacja ten interfejs definiuje zachowania i wyglądu tego typu znacznika niestandardowego.  
  
     Ten interfejs jest wywoływana, gdy  
  
    1.  Użytkownik uruchamia IDE po raz pierwszy.  
  
    2.  Użytkownik wybierze **Resetuj** przycisku w obszarze **czcionki i kolory** — strona właściwości w **środowiska** folder, znajdujący się w lewym okienku  **Opcje** okno dialogowe uzyskany z **narzędzia** menu środowiska IDE.  
  
2.  Implementowanie <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider.GetTextMarkerType%2A> metody, wskazujące, której `IVsPackageDefinedTextMarkerType` implementacji powinny być zwracane na podstawie typu znacznika GUID określony w wywołaniu metody.  
  
     Środowisko wywołuje w tej chwili Metoda pierwszego typu znacznika niestandardowego jest tworzony i określa identyfikator GUID typu znacznika niestandardowego.  
  
## <a name="to-proffer-your-marker-type-as-a-service"></a>Aby udąło typu znacznika jako usługa  
  
1.  Wywołaj <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponentManager.QueryService%2A> metodę <xref:Microsoft.VisualStudio.Shell.Interop.SProfferService>.  
  
     Wskaźnik do <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> jest zwracana.  
  
2.  Wywołaj <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.ProfferService%2A> metody, określając identyfikator GUID identyfikujący usługi typu znacznika niestandardowego i podając wskaźnik do implementacji <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> interfejsu. Twoje <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> implementacji powinna zwrócić wskaźnik do implementacji <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider> interfejsu.  
  
     Plik cookie unikatowe identyfikowanie, że usługa jest zwracana. Ten plik cookie mógł później użyć, aby można było odwołać usługi typu znacznika niestandardowego przez wywołanie metody <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> metody <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> interfejsu określenie tej wartości pliku cookie.  
  
## <a name="see-also"></a>Zobacz także  
 [Korzystanie ze znaczników tekstu przy użyciu starszej wersji interfejsu API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Porady: Dodawanie znaczników standardowy tekst](../extensibility/how-to-add-standard-text-markers.md)   
 [Porady: Implementowanie znaczniki błędów](../extensibility/how-to-implement-error-markers.md)   
 [Porady: Korzystanie ze znaczników tekstu](../extensibility/how-to-use-text-markers.md)