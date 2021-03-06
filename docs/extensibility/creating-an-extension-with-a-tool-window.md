---
title: Tworzenie rozszerzenia za pomocą okna narzędzia | Microsoft Docs
description: Dowiedz się, jak za pomocą szablonu projektu VSIX i szablonu elementu okna narzędzia niestandardowego utworzyć rozszerzenie przy użyciu okna narzędzi.
ms.custom: SEO-VS-2020
ms.date: 3/16/2019
ms.topic: how-to
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bf2bcbce3c97830663b43a94191d84d81418b423
ms.sourcegitcommit: 5027eb5c95e1d2da6d08d208fd6883819ef52d05
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2020
ms.locfileid: "94973941"
---
# <a name="create-an-extension-with-a-tool-window"></a>Tworzenie rozszerzenia za pomocą okna narzędziowego

W tej procedurze dowiesz się, jak używać szablonu projektu VSIX i szablonu elementu **okna narzędzia niestandardowego** do tworzenia rozszerzenia przy użyciu okna narzędzi.

## <a name="prerequisites"></a>Wymagania wstępne

 Począwszy od programu Visual Studio 2015, nie należy instalować zestawu Visual Studio SDK z centrum pobierania. Jest ona dostępna jako opcjonalna funkcja w Instalatorze programu Visual Studio. Zestaw VS SDK można także zainstalować później. Aby uzyskać więcej informacji, zobacz [Instalowanie zestawu Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

### <a name="create-a-tool-window"></a>Utwórz okno narzędzi

1. Utwórz projekt VSIX o nazwie **FirstWindow**. Szablon projektu VSIX można znaleźć w oknie dialogowym **Nowy projekt** , wyszukując frazę "VSIX".

2. Po otwarciu projektu Dodaj szablon elementu okna narzędzia o nazwie Moje **okno**. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy węzeł projektu i wybierz polecenie **Dodaj**  >  **nowy element**. W oknie dialogowym **Dodaj nowy element** przejdź do rozszerzalności **Visual C#**  >  **Extensibility** i wybierz **niestandardowe okno narzędzi**. W polu **Nazwa** w dolnej części okna Zmień nazwę pliku okna narzędzia na *MyWindow.cs*.

3. Skompiluj projekt i Rozpocznij debugowanie.

   Pojawia się eksperymentalne wystąpienie programu Visual Studio. Aby uzyskać więcej informacji o wystąpieniu eksperymentalnym, zobacz [wystąpienie eksperymentalne](../extensibility/the-experimental-instance.md).

4. W eksperymentalnym wystąpieniu przejdź do pozycji **Wyświetl**  >  **inne okna**.

   Powinien zostać wyświetlony element menu dla **okna**. Kliknij go.

   Powinno zostać wyświetlone okno narzędzi **z tytułem** i przyciskiem mówiącym, **kliknij mnie!.**
