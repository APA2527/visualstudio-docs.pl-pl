---
title: 'Wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu wdrażania interfejsu API ClickOnce | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, globalization
- localization, Windows Forms
- Windows Forms, localization
- globalization, ClickOnce
- satellite assemblies, ClickOnce
- ClickOnce deployment, on-demand download
- localization, ClickOnce deployment
- ClickOnce deployment, localization
ms.assetid: fdaa553f-a27e-44eb-a4e2-08c122105a87
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 506495f8be0b552f35bed0610e9fb43a77efb151
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49883032"
---
# <a name="walkthrough-download-satellite-assemblies-on-demand-with-the-clickonce-deployment-api"></a>Wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu wdrażania interfejsu API ClickOnce
Aplikacje Windows Forms można skonfigurować dla wielu języków przy użyciu zestawów satelickich. A *zestawie satelickim* to zestaw, który zawiera zasoby aplikacji dla kultury innej niż aplikacja domyślna kultura.  
  
 Zgodnie z opisem w [aplikacji ClickOnce lokalizowanie](../deployment/localizing-clickonce-applications.md), może zawierać wiele zestawów satelickich dla różnych kultur, w tym samym [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] wdrożenia. Domyślnie [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] pobierze wszystkie zestawy satelickie w danym wdrożeniu na komputerze klienckim, mimo że pojedynczego klienta, prawdopodobnie będziesz potrzebować zestawu satelickiego tylko jeden.  
  
 W tym instruktażu pokazano, jak oznaczyć swoje zestawy satelickie jako opcjonalne i Pobierz tylko zestaw na komputerze klienckim musi uzyskać bieżące ustawienia kultury. W poniższej procedurze użyto narzędzi dostępnych w ramach [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Można również wykonać to zadanie w [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  Zobacz też [wskazówki: Pobieranie zestawów satelickich na żądanie z wdrożeniem ClickOnce interfejsu API przy użyciu narzędzia Projektant](/previous-versions/visualstudio/visual-studio-2012/ms366788(v=vs.110)) lub [wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu wdrażania interfejsu API ClickOnce Projektant](/previous-versions/visualstudio/visual-studio-2013/ms366788(v=vs.120)).  
  
> [!NOTE]
>  Do celów testowych, w poniższym przykładzie kodu programowo ustawia kulturę `ja-JP`. Zobacz sekcję "Kolejne kroki" w dalszej części tego tematu zawiera informacje na temat dostosować ten kod w środowisku produkcyjnym.  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 W tym temacie założono, że wiesz, jak dodać zlokalizowane zasoby do aplikacji za pomocą programu Visual Studio. Aby uzyskać szczegółowe instrukcje, zobacz [Instruktaż: Lokalizowanie Windows forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100)).  
  
### <a name="to-download-satellite-assemblies-on-demand"></a>Aby pobrać zestawów satelickich na żądanie  
  
1. Dodaj następujący kod do aplikacji w taki sposób, aby umożliwić pobieranie zestawów satelickich na żądanie.  
  
    [!code-csharp[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]
    [!code-vb[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]  
  
2. Generowanie zestawów satelickich dla aplikacji przy użyciu [Resgen.exe (Generator pliku zasobów)](/dotnet/framework/tools/resgen-exe-resource-file-generator) lub [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
3. Generuj manifest aplikacji lub Otwórz istniejący manifest aplikacji, za pomocą *MageUI.exe*. Aby uzyskać więcej informacji o tym narzędziu, zobacz [MageUI.exe (Manifest Generation i graficzny klient Editing Tool)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client).  
  
4. Kliknij przycisk **pliki** kartę.  
  
5. Kliknij przycisk **wielokropka** przycisku (**...** ) i wybierz katalog zawierający wszystkie zestawy aplikacji i plików, w tym zestawy satelickie generowana z użyciem *Resgen.exe*. (Zestawu satelickiego mają nazwy w postaci  *\<isoCode > \ApplicationName.resources.dll*, gdzie \<isoCode > jest identyfikatorem języka, w formacie RFC 1766.)  
  
6. Kliknij przycisk **wypełniania** Aby dodać pliki do wdrożenia.  
  
7. Wybierz **opcjonalnie** pole wyboru obok każdego zestawu satelickiego.  
  
8. Ustaw pole grupy dla każdego zestawu satelickiego do jego identyfikator języka ISO. Na przykład dla zestawu satelickiego japońskiego, należy określić nazwę grupy pobierania `ja-JP`. Spowoduje to włączenie kodzie dodanym w kroku 1 do pobierania zestawu satelickiego odpowiednie, w zależności od użytkownika <xref:System.Threading.Thread.CurrentUICulture%2A> ustawienie właściwości.  
  
## <a name="next-steps"></a>Następne kroki  
 W środowisku produkcyjnym prawdopodobnie konieczne będzie usunięcie wiersza w przykładzie kodu, który ustawia <xref:System.Threading.Thread.CurrentUICulture%2A> na określoną wartość, ponieważ klient maszyny będą poprawną wartość ustawiono domyślnie. Gdy aplikacja działa na komputerze klienckim japońskiego, na przykład <xref:System.Threading.Thread.CurrentUICulture%2A> będzie `ja-JP` domyślnie. Ustawienie tej wartości programowe jest dobrym sposobem do testowania zestawów satelickich, przed wdrożeniem aplikacji.  
  
## <a name="see-also"></a>Zobacz także  
 [Lokalizowanie aplikacji ClickOnce](../deployment/localizing-clickonce-applications.md)