---
title: Eksportowanie i Zapisywanie map kodu
description: Dowiedz się, jak zapisywać mapy kodu w ramach projektu programu Visual Studio jako obrazu lub pliku XPS.
ms.custom: SEO-VS-2020
ms.date: 05/16/2018
ms.topic: how-to
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 324f8fe7ee34f469d31ad1ce6cf6bd25ab97f225
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99899820"
---
# <a name="share-code-maps"></a>Udostępnianie map kodu

Mapy kodu można zapisać jako część projektu programu Visual Studio, jako obraz lub jako plik XPS.

## <a name="share-a-code-map-with-other-visual-studio-users"></a>Udostępnianie mapy kodu innym użytkownikom programu Visual Studio

Użyj menu **plik** , aby zapisać mapę.

-lub-

Aby zapisać mapę jako część określonego projektu, na pasku narzędzi Mapa wybierz pozycję **Udostępnij**  >  **Przenieś \<CodeMapName> . dgml do**, a następnie wybierz projekt, w którym chcesz zapisać mapę.

![Przenoszenie mapy do innego projektu](../modeling/media/codemapsmovemapmenu.png)

Program Visual Studio zapisuje mapę jako plik *. dgml* , który można udostępniać innym użytkownikom Visual Studio Enterprise i Visual Studio Professional.

> [!NOTE]
> Przed udostępnieniem mapy z tymi, które używają Visual Studio Professional, pamiętaj, aby rozwinąć wszystkie grupy, pokazać ukryte węzły i linki między grupami i pobrać wszystkie usunięte węzły, które mają być widoczne dla innych użytkowników na mapie. W przeciwnym razie inni użytkownicy nie będą mogli zobaczyć tych elementów.
>
> Następujący błąd może wystąpić, gdy zapisujesz mapę, która znajduje się w projekcie modelowania lub został skopiowany z projektu modelowania do innej lokalizacji:
>
> "Nie można zapisać *pliku* poza katalogiem projektu. Elementy połączone nie są obsługiwane”.
>
> Program Visual Studio pokazuje błąd, ale mimo to tworzy zapisaną wersję. Aby uniknąć tego błędu, Utwórz mapę poza projektem modelowania. Można następnie zapisać go w dowolnej lokalizacji. Skopiowanie pliku do innej lokalizacji w rozwiązaniu, a następnie próba zapisu zakończą się niepowodzeniem.

## <a name="export-a-code-map-as-an-image"></a>Eksportowanie mapy kodu jako obrazu

Podczas eksportowania mapy kodu jako obrazu można skopiować ją do innych aplikacji, takich jak Microsoft Word lub PowerPoint.

1. Na pasku narzędzi Mapa kodu wybierz opcję **Udostępnij**  >  **wiadomość e-mail jako obraz** lub **Kopiuj obraz**.

2. Wklej obraz do innej aplikacji.

## <a name="export-the-map-as-an-xps-file"></a>Eksportowanie mapy jako pliku XPS

Podczas eksportowania mapy kodu jako pliku XPS można ją zobaczyć w przeglądarkach XML lub XAML, takich jak program Internet Explorer.

1. Na pasku narzędzi Mapa kodu wybierz opcję **Udostępnij**  >  **wiadomość e-mail jako przenośny dokument XPS** lub **Zapisz jako przenośny plik XPS**.

2. Przejdź do lokalizacji, w której chcesz zapisać plik.

3. Nazwij mapę kodu. Upewnij się, że pole **Zapisz jako typ** jest ustawione na **pliki XPS ( \* . XPS)**. Wybierz polecenie **Zapisz**.

## <a name="see-also"></a>Zobacz też

- [Mapowanie zależności za pomocą map kodu](../modeling/map-dependencies-across-your-solutions.md)
