---
title: Hierarchiczna organizacja zasobów do lokalizacji | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- resource files, localized
- localization [Visual Studio], resources
- fallback resources
- international applications [Visual Studio], storing resources
- satellite assemblies, resource hierarchies
- globalization [Visual Studio], resources
- satellite assemblies
- resources [Visual Studio], fallback system
- resource files, fallback processes
ms.assetid: dadf8f2c-f74c-44d7-bec0-a1e956d8d38d
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0e07d788f17469ab7a478f22dcf3aeffacfa9220
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681830"
---
# <a name="hierarchical-organization-of-resources-for-localization"></a>Hierarchiczna organizacja zasobów do lokalizacji
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

W programie Visual Studio zlokalizowane zasoby (dane, takie jak ciągi i odpowiednie do poszczególnych kultur obrazów) są przechowywane w oddzielnych plikach i załadować zgodnie z ustawieniem kultury interfejsu użytkownika. Aby zrozumieć, w jaki sposób zlokalizowane zasoby są ładowane, warto traktować je jak zorganizowane hierarchicznie.  
  
## <a name="kinds-of-resources-in-the-hierarchy"></a>Rodzaje zasobów w hierarchii  
  
-   Na początku hierarchii znajdują się zasoby rezerwowe dla Twojej domyślnej kultury, na przykład język angielski ("PL"). Są to jedyne zasoby, które nie mają własnych plików; są one przechowywane w głównym zestawie.  
  
-   Poniższe zasoby rezerwowe są zasoby dla dowolnej kultury neutralnej. Kultury neutralnej jest skojarzony z innym języku, ale nie kraj/region. Na przykład francuski ("fr") jest kultury neutralnej. (Należy pamiętać, że zasoby rezerwowe są również dla kultury neutralnej, ale wspaniałe.)  
  
-   Pod tymi są zasoby dla dowolnej określonych kultur. Określonej kultury jest skojarzony z języka i kraju/regionu. Na przykład francuski kanadyjski ("fr-CA") jest określonej kultury.  
  
 Jeśli aplikacja próbuje załadować żadnych zlokalizowany zasób, takie jak ciąg i nie zostanie znaleziona, aż do znalezienia pliku zasobu zawierającego żądanego zasobu będą przesyłane w hierarchii.  
  
 Najlepszym sposobem przechowywania zasobów jest uogólniać je w miarę możliwości. Oznacza to, do przechowywania zlokalizowane ciągi, obrazy i innych elementów w plikach zasobów dla kultury neutralnej zamiast określonych kultur, jeśli to możliwe. Na przykład jeśli zasoby dla Belgii francuski ("fr-być") kultury i natychmiast wspomniane zasoby znajdują się zasoby rezerwowe w języku angielskim, problem może spowodować, gdy ktoś będzie korzystać z aplikacji w systemie, skonfigurowane dla kultury francuski kanadyjski. System będzie szukać zestawu satelickiego dla "fr-CA", nie go znaleźć i załadować zestawu głównego, zawierający bazoey zasoby, jest język angielski, zamiast ładowanie zasobów francuska. Na poniższej ilustracji przedstawiono w tym scenariuszu niepożądane.  
  
 ![Tylko określone zasoby](../ide/media/vbspecificresourcesonly.gif "vbSpecificResourcesOnly")  
  
 W przypadku postępuj zgodnie z zalecaną praktyką składania tylu zasobów, jak to możliwe w pliku zasobów neutralnej kultury "fr", francuski kanadyjski użytkownika nie widział zasoby oznaczone na "fr-być" kultury, ale dany użytkownik zostaną pokazane ciągi w języku francuskim. Następującej sytuacji pokazuje, w tym scenariuszu preferowany.  
  
 ![NeutralSpecificResources — grafika](../ide/media/vbneutralspecificresources.gif "vbNeutralSpecificResources")  
  
## <a name="see-also"></a>Zobacz też  
 [Neutralny język zasobów dla lokalizacji](../ide/neutral-resources-languages-for-localization.md)   
 [Zabezpieczenia a zlokalizowane zestawy satelickie](../ide/security-and-localized-satellite-assemblies.md)   
 [Lokalizowanie aplikacji](../ide/localizing-applications.md)   
 [Globalizacja i lokalizacja aplikacji](../ide/globalizing-and-localizing-applications.md)   
 [Porady: Ustawianie kultury i kultury UI dla globalizacji formularzy Windows](http://msdn.microsoft.com/en-us/694e049f-0b91-474a-9789-d35124f248f0)   
 [Porady: Ustawianie kultury i kultury UI dla globalizacji strony sieci Web platformy ASP.NET](http://msdn.microsoft.com/library/76091f86-f967-4687-a40f-de87bd8cc9a0)

