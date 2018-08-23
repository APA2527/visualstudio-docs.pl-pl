---
title: Zabezpieczenia w programie Visual Studio | Dokumentacja firmy Microsoft
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
- code access security, coding errors
- security [.NET Framework], about security
ms.assetid: 318c34ce-f643-468c-83a1-843196f5d845
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5952b42426f09a0f6e3bcdb6faf318774165f587
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627727"
---
# <a name="security-in-visual-studio"></a>Zabezpieczenia w Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [zabezpieczeń w programie Visual Studio](https://docs.microsoft.com/visualstudio/ide/security-in-visual-studio).  
  
Należy rozważyć bezpieczeństwo we wszystkich aspektach programowania aplikacji, od projektowania do wdrożenia. Rozpocznij od uruchamianie programu Visual Studio w bezpieczny sposób. Zobacz [uprawnienia użytkownika](../ide/user-permissions-and-visual-studio.md).  
  
 Aby efektywnie rozwijać bezpieczne aplikacje, powinieneś rozumieć podstawy pojęć związanych z bezpieczeństwem i funkcji zabezpieczeń platform, dla których tworzysz. Należy również mieć świadomość bezpiecznych technik kodowania.  
  
## <a name="understanding-security"></a>Opis zabezpieczeń  
 [Zabezpieczenia](http://msdn.microsoft.com/library/9a9621d7-8883-4a4f-a874-65e8e09e20a6)  
 Opisuje zabezpieczenia dostępu do kodu .NET Framework, zabezpieczenia oparte na rolach, zasady zabezpieczeń i narzędzia zabezpieczeń.  
  
 [Obrony kodu przy użyciu dziesięciu najlepszych wskazówek dotyczących bezpieczeństwa, które każdy deweloper musi znać](http://go.microsoft.com/fwlink/?LinkId=72877)  
 W tym artykule opisano problemy, na które należy zwrócić uwagę, aby nie naruszyć danych lub systemu.  
  
## <a name="coding-for-security"></a>Bezpieczne kodowanie  
 Większość błędów kodowania, które powodują powstanie luk w zabezpieczeniach, występuje, ponieważ deweloperzy mogą stosować błędne założenia podczas pracy z danymi wejściowymi użytkownika lub ponieważ nie w pełni rozumieją platformę, dla której tworzą.  
  
 [Wytyczne dotyczące bezpiecznego programowania](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)  
 Zawiera wskazówki dotyczące klasyfikacji składników, aby rozwiązywać problemy z bezpieczeństwem.  
  
 [Najlepsze rozwiązania dotyczące zabezpieczeń](http://msdn.microsoft.com/library/86acaccf-cdb4-4517-bd58-553618e3ec42)  
 W tym artykule omówiono przepełnienia bufora oraz pełny obraz funkcji kontroli zabezpieczeń Microsoft Visual C++, dostarczanej przez flagę czasu kompilacji /GS.



