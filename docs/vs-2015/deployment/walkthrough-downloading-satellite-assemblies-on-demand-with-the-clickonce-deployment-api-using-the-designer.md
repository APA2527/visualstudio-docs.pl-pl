---
title: 'Wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu wdrażania ClickOnce interfejsu API przy użyciu narzędzia Projektant | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows Forms, globalization
- ClickOnce deployment, globalization
- localization, Windows Forms
- ClickOnce, on-demand download
- Windows Forms, localization
- ClickOnce deployment, localization
- walkthroughs, localization
ms.assetid: 82b85a47-b223-4221-a17c-38a52c3fb6e2
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 8ed393a17c3489e0133a4a6534deb8f2dab1e428
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684798"
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer"></a>Wskazówki: pobieranie zestawów satelickich na żądanie przy użyciu wdrażania interfejsu API ClickOnce za pomocą Projektanta
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu technologii ClickOnce wdrażania interfejsu API przy użyciu narzędzia Projektant](https://docs.microsoft.com/visualstudio/deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer).  
  
Aplikacje Windows Forms można skonfigurować dla wielu języków przy użyciu zestawów satelickich. A *zestawie satelickim* to zestaw, który zawiera zasoby aplikacji dla kultury innej niż aplikacja domyślna kultura.  
  
 Zgodnie z opisem w [lokalizowanie aplikacji ClickOnce](../deployment/localizing-clickonce-applications.md), może zawierać wiele zestawów satelickich dla różnych kultur, w tym samym [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] wdrożenia. Domyślnie [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] pobierze wszystkie zestawy satelickie w danym wdrożeniu na komputerze klienckim, mimo że pojedynczego klienta, prawdopodobnie będziesz potrzebować zestawu satelickiego tylko jeden.  
  
 W tym instruktażu pokazano, jak oznaczyć swoje zestawy satelickie jako opcjonalne i Pobierz tylko zestaw na komputerze klienckim musi uzyskać bieżące ustawienia kultury.  
  
> [!NOTE]
>  Do celów testowych, w poniższych przykładach kodu programowo równa kulturę `ja-JP`. Zobacz sekcję "Kolejne kroki" w dalszej części tego tematu zawiera informacje na temat dostosować ten kod w środowisku produkcyjnym.  
  
### <a name="to-mark-satellite-assemblies-as-optional"></a>Aby oznaczyć jako opcjonalne zestawy satelickie  
  
1.  Skompilowanie projektu. Spowoduje to wygenerowanie zestawów satelickich dla wszystkich kultur, w których lokalizujesz do.  
  
2.  Kliknij prawym przyciskiem myszy nazwę projektu w Eksploratorze rozwiązań, a następnie kliknij przycisk **właściwości**.  
  
3.  Kliknij przycisk **Publikuj** kartę, a następnie kliknij przycisk **pliki aplikacji**.  
  
4.  Wybierz **Pokaż wszystkie pliki** pole wyboru, aby wyświetlić zestawy satelickie. Domyślnie wszystkie zestawy satelickie zostaną uwzględnione we wdrożeniu i będą widoczne w tym oknie dialogowym.  
  
     Zestawu satelickiego mają nazwy w postaci *isoCode*\ApplicationName.resources.dll, gdzie *isoCode* jest w formacie RFC 1766 identyfikator języka.  
  
5.  Kliknij przycisk **nowy...**  w **grupa pobierania** listy dla każdego identyfikatora języka. Po wyświetleniu monitu Pobierz nazwę grupy, należy wprowadzić identyfikator języka. Na przykład dla zestawu satelickiego japońskiego, należy określić nazwę grupy pobierania `ja-JP`.  
  
6.  Zamknij **pliki aplikacji** okno dialogowe.  
  
### <a name="to-download-satellite-assemblies-on-demand-in-c"></a>Aby pobrać zestawów satelickich na żądanie w języku C#  
  
1.  Otwórz plik Program.cs. Jeśli nie widzisz tego pliku w Eksploratorze rozwiązań, wybierz swój projekt, a na **projektu** menu, kliknij przycisk **Pokaż wszystkie pliki**.  
  
2.  Użyj poniższego kodu, aby pobrać zestawu satelickiego odpowiednie i uruchomić aplikację.  
  
     [!code-csharp[ClickOnce.SatelliteAssemblies#1](../snippets/csharp/VS_Snippets_Winforms/ClickOnce.SatelliteAssemblies/CS/Program.cs#1)]  
  
### <a name="to-download-satellite-assemblies-on-demand-in-visual-basic"></a>Aby pobrać zestawów satelickich na żądanie w języku Visual Basic  
  
1.  W **właściwości** okna aplikacji, kliknij przycisk **aplikacji** kartę.  
  
2.  W dolnej części strony karty kliknij **Wyświetl zdarzenia aplikacji**.  
  
3.  Dodaj następujące instrukcje importu na początku pliku ApplicationEvents.VB.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#1](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnce.SatelliteAssembliesVB/VB/ApplicationEvents.vb#1)]  
  
4.  Dodaj następujący kod do `MyApplication` klasy.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#2](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnce.SatelliteAssembliesVB/VB/ApplicationEvents.vb#2)]  
  
## <a name="next-steps"></a>Następne kroki  
 W środowisku produkcyjnym prawdopodobnie konieczne będzie usunięcie wiersza w przykłady kodu, które ustawia <xref:System.Threading.Thread.CurrentUICulture%2A> na określoną wartość, ponieważ klient maszyny będą poprawną wartość ustawiono domyślnie. Gdy aplikacja działa na komputerze klienckim japońskiego, na przykład <xref:System.Threading.Thread.CurrentUICulture%2A> będzie `ja-JP` domyślnie. Ustawieniem dla niego programowe jest dobrym sposobem do testowania zestawów satelickich, przed wdrożeniem aplikacji.  
  
## <a name="see-also"></a>Zobacz też  
 [Wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu wdrażania interfejsu API ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)   
 [Lokalizowanie aplikacji ClickOnce](../deployment/localizing-clickonce-applications.md)



