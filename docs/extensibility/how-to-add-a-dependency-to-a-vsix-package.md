---
title: 'Instrukcje: Dodawanie zależności do pakietu VSIX | Microsoft Docs'
description: Dowiedz się, jak skonfigurować wdrożenie pakietu VSIX, które instaluje wszystkie zależności, które nie znajdują się jeszcze na komputerze docelowym.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d7ef19bafd0788ed15094979141679625e4e992f
ms.sourcegitcommit: d10f37dfdba5d826e7451260c8370fd1efa2c4e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2020
ms.locfileid: "96993838"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Instrukcje: Dodawanie zależności do pakietu VSIX

Można skonfigurować wdrożenie pakietu VSIX, które instaluje wszystkie zależności, które nie znajdują się jeszcze na komputerze docelowym. Aby to osiągnąć, Uwzględnij zależności VSIX do pliku *source. Extension. vsixmanifest* .

## <a name="to-add-a-dependency"></a>Aby dodać zależność

1. Otwórz plik *source. Extension. vsixmanifest* w widoku **projektu** . Przejdź do karty **zależności** i kliknij pozycję **Nowy**.

2. Aby dodać zainstalowane rozszerzenie: w oknie dialogowym **Dodaj nową zależność** wybierz **zainstalowane rozszerzenie** , a następnie w polu **Nazwa** wybierz rozszerzenie na liście.

3. Aby dodać inny VSIX, który nie jest zainstalowany: w oknie dialogowym **Dodaj nową zależność** wybierz pozycję **plik w systemie plików** , a następnie użyj przycisku **Przeglądaj** , aby wybrać VSIX.

## <a name="require-a-specific-visual-studio-release"></a>Wymagaj określonej wersji programu Visual Studio

Jeśli rozszerzenie wymaga określonej wersji programu Visual Studio 2017, na przykład zależy od funkcji wydanej w 15,3, można określić numer kompilacji w **INSTALLATIONTARGET** VSIX. Na przykład wersja 15,3 ma numer kompilacji "15.0.26730.3". W [tym miejscu](../install/visual-studio-build-numbers-and-release-dates.md)możesz zobaczyć mapowanie wydań, aby kompilować numery. Należy pamiętać, że użycie numeru wydania "15,3" nie będzie działało poprawnie.

Jeśli rozszerzenie wymaga 15,3 lub nowszego, należy zadeklarować **wersję InstallationTarget** jako [15.0.26730.3, 16,0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```

Instalator VSIX wykrywa wcześniejsze wersje programu Visual Studio i informuje użytkownika, że wymagana jest nowsza aktualizacja.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja schematu rozszerzenia VSIX 1,0](/previous-versions/dd393700(v=vs.110))
- [Anatomia pakietu VSIX](../extensibility/anatomy-of-a-vsix-package.md)
- [Przygotuj rozszerzenia dla wdrożenia Instalator Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)