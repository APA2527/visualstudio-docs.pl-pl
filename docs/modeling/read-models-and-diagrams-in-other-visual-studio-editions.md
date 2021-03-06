---
title: Odczytywanie modeli i diagramów w innych wersjach programu Visual Studio
description: Dowiedz się więcej na temat odczytywania modeli i diagramów w programie Visual Studio, a także zachowania tylko do odczytu w przypadku korzystania z wersji programu Visual Studio, która nie obsługuje tworzenia modelu.
ms.custom: SEO-VS-2020
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: JoshuaPartlow
ms.author: joshuapa
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: a8049471e9e172496381df016c6155410f3bc244
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99882937"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Odczytywanie modeli i diagramów w innych wersjach programu Visual Studio

Po otwarciu modelu w wersji programu Visual Studio, która nie obsługuje tworzenia modelu, model zostanie otwarty w trybie tylko do odczytu. W tym trybie można zmienić układ diagramów, ale nie można zmienić modelu.

Aby sprawdzić, które wersje programu Visual Studio obsługują tworzenie modelu, zobacz [Obsługa wersji dla narzędzi architektury i modelowania](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="obtaining-access-to-a-model-and-diagrams"></a>Uzyskiwanie dostępu do modelu i diagramów

Aby odczytać diagram zależności, należy najpierw użyć programu Visual Studio, aby otworzyć projekt modelowania, a następnie otworzyć go w obrębie tego diagramu.

Z tego powodu, jeśli chcesz odczytać diagram zależności, musisz również mieć dostęp do projektu modelowania, w którym został utworzony. Można to zrobić przez uzyskanie dostępu do projektu z kontroli źródła lub uzyskanie kopii plików projektu.

> [!NOTE]
> Nie dotyczy to map kodu i diagramów klas .NET generowanych na podstawie kodu. Te diagramy mogą być wyświetlane niezależnie od projektu modelowania.

Aby odczytać diagram zależności, minimalny zestaw wymaganych plików jest następujący:

- Dwa pliki diagramu dla diagramu, który ma zostać odczytany, na przykład, **Webdiagrams. classdiagram i webdiagram. classdiagram. layout**.

    > [!NOTE]
    > W przypadku diagramów zależności należy również mieć plik o nazwie Moje _Diagram_**. layerdiagram. pominięcia**.

- Plik projektu modelowania (**WebMode. modelproj**)

- Plik modelu głównego (**ModelDefinition\MyModel.UML**)

- Pliki pakietu dla dowolnego pakietu, do którego odwołuje się Diagram (**ModelDefinition\MyPackage.UML**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>Zmiany, które można wprowadzić w trybie Read-Only

Jeśli otworzysz model i jego diagramy w wersji programu Visual Studio, która nie obsługuje tworzenia modelu, nie możesz zmienić modelu. Oznacza to, że nie można zmienić elementów i relacji, które są wyświetlane na diagramach lub w Eksploratorze modelu. Można jednak wprowadzić pewne zmiany w układzie diagramów:

- Zmień rozmieszczenie kształtów i łączników na diagramie.

- Rozwijanie i zwijanie kształtów.

Można zapisać te zmiany. Jeśli chcesz, aby zmiany były widoczne dla innych użytkowników, musisz mieć co najmniej wysłanie zaktualizowanych plików **układu** .

## <a name="see-also"></a>Zobacz też

- [Diagramy zależności: Odwołanie](../modeling/layer-diagrams-reference.md)
- [Tworzenie modeli aplikacji](../modeling/create-models-for-your-app.md)
