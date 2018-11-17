---
title: 'Porady: aktualizowanie rozszerzenia programu Visual Studio | Dokumentacja firmy Microsoft'
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
- update package
- update extension
- new package version
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f4dce6301e5f55dce2c9786033ca895e0ac43518
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2018
ms.locfileid: "51721042"
---
# <a name="how-to-update-a-visual-studio-extension"></a>Porady: aktualizowanie rozszerzenia programu Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Można zaktualizować rozszerzenia programu Visual Studio w systemie przy użyciu **rozszerzenia i aktualizacje** zainstalować zaktualizowaną wersję. Jeśli tworzysz zaktualizowaną wersję rozszerzenia, oznaczyć go jako zaktualizowany przez zwiększenie numeru wersji manifestu VSIX.  
  
 Aktualizacje są instalowane podczas manifestu VSIX przychodzących rozszerzenia ma taką samą `ID` jako zainstalowaną wersją i uzyskanie lepszej `Version` numer. Jeśli `Version` numer jest taki sam lub niższy, nie można zainstalować pakietu. Jeśli `ID` wartości nie są zgodne, pakiet, który nie jest jeszcze zainstalowany jest rozpoznawana jako osobne rozszerzenie.  
  
 Aby uniknąć konfliktów podczas programowania, zaleca się, czy odinstalowaniu wcześniejszych wersji rozszerzenia w toku, a także Odinstaluj lub wyłącz inne rozszerzenia mogą powodować konflikt.  
  
### <a name="to-update-an-extension-on-your-system"></a>Można zaktualizować rozszerzenia w systemie  
  
1.  Na **narzędzia** menu, kliknij przycisk **rozszerzenia i aktualizacje**.  
  
2.  W okienku po lewej stronie kliknij **aktualizacje**.  
  
3.  W środkowym okienku kliknij aktualizacji, którą chcesz zainstalować.  
  
     Numer wersji zaktualizowane rozszerzenie jest wyświetlana w okienku po prawej stronie, oraz inne informacje.  
  
4.  W dolnym okienku po prawej stronie, kliknij **aktualizacji**.  
  
### <a name="to-publish-an-update-of-an-extension"></a>Aby opublikować aktualizację rozszerzenia  
  
1.  W programie Visual Studio Otwórz rozwiązanie dla rozszerzenia, które chcesz zaktualizować. Wprowadź zmiany.  
  
    > [!IMPORTANT]
    >  Niepodpisane wszystkie rozszerzenia użytkowników nie zostaje zaktualizowana automatycznie. Należy zawsze utworzyć rozszerzeń.  
  
2.  W **Eksploratora rozwiązań**, otwórz source.extension.manifest.  
  
3.  W Projektancie manifestu, należy zwiększyć wartość liczby w parametrze **wersji** pola.  
  
4.  Zapisywanie rozwiązania i skompiluj je.  
  
5.  Przekaż nowy plik .vsix (w folderze \bin\Debug\ projektu), aby [galerii Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) witryny sieci Web.  
  
     Po otwarciu użytkownik, który ma wcześniejszą wersję rozszerzenia **rozszerzenia i aktualizacje**, nowa wersja pojawi się w **aktualizacje** listy, pod warunkiem, że narzędzie ma wartość automatycznie wyszukać aktualizacje.  
  
     Można włączyć lub wyłączyć automatyczne sprawdzanie dostępności aktualizacji w dolnej części **aktualizacje** okienko (**Włącz/Wyłącz automatyczne wykrywanie dostępnych aktualizacji**), które zmiany **Wyszukaj aktualizacje** w **narzędzia / Opcje / środowisko / rozszerzenia i aktualizacje**.  
  
    > [!NOTE]
    >  Począwszy od programu Visual Studio 2015 Update 2, można określić (w **narzędzia / Opcje / środowisko / rozszerzenia i aktualizacje**) czy będzie automatyczne aktualizacje dla rozszerzenia dla poszczególnych użytkowników, wszystkie rozszerzenia użytkowników lub obie (ustawienie domyślne).  
  
## <a name="see-also"></a>Zobacz też  
 [Anatomia pakietu VSIX](../extensibility/anatomy-of-a-vsix-package.md)   
 [Znajdowanie rozszerzeń programu Visual Studio i korzystanie z nich](../ide/finding-and-using-visual-studio-extensions.md)

