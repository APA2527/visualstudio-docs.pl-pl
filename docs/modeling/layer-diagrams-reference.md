---
title: Odwołania do diagramów zależności
description: Dowiedz się, że w programie Visual Studio można użyć diagramu zależności do wizualizacji logicznej architektury systemu.
ms.custom: SEO-VS-2020
ms.date: 09/28/2018
ms.topic: reference
f1_keywords:
- vs.teamarch.layerdiagram.layerexplorer.artifactlink
- vs.teamarch.layerdiagram.layerexplorer.artifactlink.properties
- vs.teamarch.layerdiagram.diagram
- vs.teamarch.UMLModelExplorer.layerdiagram
- vs.teamarch.layerdiagram.layerexplorer
- vs.teamarch.layerdiagram.shapes.properties
- vs.teamarch.layerdiagram.toolbox
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: f173e27588538c806d075e0a6b010fbd848f2690
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99916997"
---
# <a name="dependency-diagrams-reference"></a>Diagramy zależności: odwołanie

W programie Visual Studio można użyć *diagramu zależności* do wizualizacji architektury logicznej wysokiego poziomu w systemie. Diagram zależności organizuje fizyczne artefakty w systemie jako logiczne, abstrakcyjne grupy o nazwie *warstwy*. Te warstwy opisują najważniejsze zadania wykonywane przez artefakty lub główne składniki systemu. Każda warstwa może również zawierać zagnieżdżone warstwy, które opisują bardziej szczegółowe zadania.

Aby sprawdzić, które wersje programu Visual Studio obsługują tę funkcję, zobacz [Obsługa wersji dla narzędzi architektury i modelowania](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

> [!NOTE]
> Diagramy zależności dla projektów .NET Core są obsługiwane począwszy od programu Visual Studio 2019 w wersji 16,2.

Można określić zamierzone lub istniejące zależności między warstwami. Te zależności, które są reprezentowane jako strzałki, wskazują, które warstwy mogą używać lub obecnie używają funkcji reprezentowanych przez inne warstwy. Organizując system do warstw, które opisują różne role i funkcje, diagram zależności może pomóc ułatwić zrozumienie, ponowne użycie i konserwację kodu.

Użyj diagramu zależności, aby ułatwić wykonywanie następujących zadań:

- Przekazanie istniejącej lub zamierzonej logicznej architektury systemu.

- Odkryj konflikty między istniejącym kodem a zamierzoną architekturą.

- Wizualizuj wpływ zmian w zamierzonej architekturze podczas refaktoryzacji, aktualizowania lub rozwijania systemu.

- Zapoznaj się z zamierzoną architekturą podczas opracowywania i konserwowania kodu przez uwzględnienie walidacji operacji ewidencjonowania i kompilowania.

W tym temacie opisano elementy, których można użyć na diagramie zależności. Aby uzyskać szczegółowe informacje na temat tworzenia i rysowania diagramów zależności, zobacz [diagramy zależności: wytyczne](../modeling/layer-diagrams-guidelines.md). Aby uzyskać więcej informacji na temat wzorców warstwowych, odwiedź [witrynę wzorców & Practices](https://archive.codeplex.com/?p=apparch).

## <a name="reading-dependency-diagrams"></a>Odczytywanie diagramów zależności

![Elementy na diagramach zależności](../modeling/media/uml_layerrefreading.png)

W poniższej tabeli opisano elementy, których można użyć na diagramie zależności.

|**Przekształca**|**Element**|**Opis**|
|-|-|-|
|1|**Warstwa**|Logiczna Grupa artefaktów fizycznych w systemie. Te artefakty mogą być przestrzeniami nazw, projektami, klasami, metodami i tak dalej.<br /><br /> Aby wyświetlić artefakty, które są połączone z warstwą, otwórz menu skrótów dla warstwy, a następnie wybierz polecenie **Wyświetl linki** , aby otworzyć **Eksploratora warstw**.<br /><br /> Aby uzyskać więcej informacji, zobacz [Eksplorator warstw](#Explorer).<br /><br /> -   **Zależności przestrzeni nazw zabronione** — określa, że artefakty skojarzone z tą warstwą nie mogą zależeć od określonych przestrzeni nazw.<br />-   **Niedozwolone przestrzenie nazw** — określa, że artefakty skojarzone z tą warstwą nie mogą należeć do określonych przestrzeni nazw.<br />-   **Wymagane przestrzenie nazw** — określa, że artefakty skojarzone z tą warstwą muszą należeć do jednej z określonych przestrzeni nazw.|
|2|**Zależność**|Wskazuje, że jedna warstwa może korzystać z funkcjonalności w innej warstwie, ale nie odwrotnie.<br /><br /> -   **Direction** — określa kierunek zależności.|
|3|**Zależność dwukierunkowa**|Wskazuje, że jedna warstwa może korzystać z funkcjonalności w innej warstwie i na odwrót.<br /><br /> -   **Direction** — określa kierunek zależności.|
|4|**Komentarz**|Służy do dodawania ogólnych notatek do diagramu lub elementów na diagramie.|
|5|**Link komentarza**|Służy do łączenia komentarzy do elementów na diagramie.|

## <a name="layer-explorer"></a><a name="Explorer"></a> Eksplorator warstw

Możesz połączyć każdą warstwę z artefaktami w rozwiązaniu, takich jak projekty, klasy, przestrzenie nazw, pliki projektu i inne części oprogramowania. Liczba na warstwie pokazuje liczbę artefaktów, które są połączone z warstwą. Jednak podczas odczytywania liczby artefaktów na warstwie należy pamiętać o następujących kwestiach:

- Jeśli warstwa jest połączona z artefaktem zawierającym inne artefakty, ale warstwy nie łączy się bezpośrednio z innymi artefaktami, wówczas liczba uwzględnia tylko połączony artefakt. Jednak inne artefakty są uwzględniane w analizie podczas walidacji warstwy.

     Na przykład, jeżeli warstwa jest połączona z pojedynczą przestrzenią nazw, liczba połączonych artefaktów wynosi 1, nawet jeśli przestrzeń nazw zawiera klasy. Jeśli warstwa zawiera także łącza do każdej klasy w przestrzeni nazw, liczba będzie uwzględniać połączone klasy.

- Jeśli warstwa zawiera inne warstwy, które są połączone z artefaktami, warstwa kontenerów jest także połączona z tymi artefaktami, mimo że liczba na warstwie kontenerów nie uwzględnia tych artefaktów.

Aby uzyskać więcej informacji na temat łączenia warstw i artefaktów, zobacz:

- [Diagramy zależności: wskazówki](../modeling/layer-diagrams-guidelines.md)

- [Tworzenie diagramów zależności z kodu](../modeling/create-layer-diagrams-from-your-code.md)

### <a name="examine-the-linked-artifacts"></a>Sprawdzanie połączonych artefaktów

Na diagramie zależności Otwórz menu skrótów dla jednej lub wielu warstw, a następnie wybierz polecenie **Wyświetl linki**.

**Eksplorator warstwy** otwiera i pokazuje artefakty, które są połączone z wybranymi warstwami. **Eksplorator warstw** zawiera kolumnę, która zawiera wszystkie właściwości linków artefaktów.

> [!NOTE]
> Jeśli nie są widoczne wszystkie te właściwości, rozwiń okno **Eksplorator warstwy** .

|**Kolumna w Eksploratorze warstwy**|**Opis**|
|-|-|
|**Kategorie**|Rodzaj artefaktu, taki jak Klasa, przestrzeń nazw, plik źródłowy itd.|
|**Warstwa**|Warstwa, która łączy się z artefaktem|
|**Obsługuje walidację**|W przypadku **wartości true** proces walidacji warstwy może sprawdzić, czy projekt jest zgodny z zależnościami lub z tego elementu.<br /><br /> W przypadku **wartości false** link nie uczestniczy w procesie walidacji warstwy.<br /><br /> Aby uzyskać więcej informacji, zobacz [diagramy zależności: wytyczne](../modeling/layer-diagrams-guidelines.md).|
|**Identyfikator**|Odwołanie do połączonego artefaktu|

## <a name="see-also"></a>Zobacz też

- [Tworzenie modeli aplikacji](../modeling/create-models-for-your-app.md)
