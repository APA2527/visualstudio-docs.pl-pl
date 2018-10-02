---
title: Odczytywanie modeli i diagramów w innych wersjach programu Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: cfd6188bc4d48f26e85ae8778d75d2fa99ef0f25
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859682"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Odczytywanie modeli i diagramów w innych wersjach programu Visual Studio
Po otwarciu modelu w wersji programu Visual Studio, który nie obsługuje tworzenia modelu modelu zostanie otwarty w trybie tylko do odczytu. W tym trybie można zmienić układ diagramy, ale nie można zmienić modelu.

 Aby dowiedzieć się, które wersje programu Visual Studio obsługują tworzenie modelu, zobacz [obsługiwana wersja dla narzędzia architektury i modelowania](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="obtaining-access-to-a-model-and-diagrams"></a>Uzyskiwanie dostępu do modeli i diagramów
 Do odczytywania diagram zależności, należy najpierw przy użyciu programu Visual Studio Otwórz projekt modelowania, a następnie Otwórz diagram znajdujący się w nim.

 Z tego powodu jeśli chcesz odczytać diagram zależności, należy również masz dostęp do projektu modelowania, w której został utworzony. Można to zrobisz, uzyskując dostęp do projektu z kontroli źródła lub przez uzyskanie kopii plików projektu.

> [!NOTE]
>  To nie ma zastosowania do kodu mapy i .NET klasy diagramy wygenerowane z kodu. Można wyświetlić tych diagramów, niezależnie od projektu modelowania.

 Aby uzyskać diagram zależności, minimalny zestaw plików, które są potrzebne jest następująca:

-   Dwa pliki dla diagramu, który chcesz, aby dowiedzieć się, na przykład diagramu **MyDiagram.classdiagram i MyDiagram.classdiagram.layout**.

    > [!NOTE]
    >  Dla diagramów zależności powinien również mieć plik o nazwie _MyDiagram_**. layerdiagram.suppressions**.

-   Pliku projektu modelowania (**MyModel.modelproj**)

-   Plik modelu głównym (**ModelDefinition\MyModel.uml**)

-   Pliki pakietu dla dowolnego pakietu, do którego odwołuje się na diagramie (**ModelDefinition\MyPackage.uml**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>Zmiany wprowadzone w trybie tylko do odczytu
 Jeśli otworzysz modelu i jego diagramy w wersjach programu Visual Studio, który nie obsługuje tworzenia modelu, nie można zmienić modelu. Oznacza to, że nie można zmienić elementów i relacji, które są wyświetlane na diagramach lub w Eksploratorze modelu. Można jednak wprowadzić pewne zmiany, układu tych diagramów:

-   Rozmieszczanie kształtów i łączników na diagramie.

-   Rozwijanie i zwijanie kształtów.

 Możesz zapisać te zmiany. Jeśli chcesz zmiany były widoczne dla innych użytkowników, co najmniej trzeba wysłać zaktualizowany **.layout** plików.

## <a name="RelatedTopics"></a> Tematy pokrewne

|Tytuł|Opis|
|-----------|-----------------|
|[Diagramy zależności: Odwołanie](../modeling/layer-diagrams-reference.md)|Diagram warstwowy pokazuje strukturę ogólną architekturę. Gdy kod jest zapisywany, mogą być automatycznie sprawdzone podstawie diagramu warstwowego.|

## <a name="see-also"></a>Zobacz też

- [Tworzenie modeli aplikacji](../modeling/create-models-for-your-app.md)