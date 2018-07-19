---
title: 'Porady: tworzenie cieniowania tekstury podstawowej'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 5af113fb-6415-4be0-8b23-10fddb10e80a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 211da971bc7e4e275ef43b88531fe46a7fc0b4eb
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924069"
---
# <a name="how-to-create-a-basic-texture-shader"></a>Porady: tworzenie cieniowania tekstury podstawowej

W tym artykule pokazano, jak używać Shader Designer i język programu do cieniowania wykres kierowany (DGSL) do tworzenia modułu cieniującego jednego tekstury. Ten program do cieniowania Ustawia kolor końcowy bezpośrednio RGB i wartości alfa, które są próbkowane z tekstury.

## <a name="create-a-basic-texture-shader"></a>Tworzenie cieniowania tekstury podstawowej

Podstawowa, jednego tekstury modułu cieniującego można zaimplementować, pisząc wartości kolorów i alfa próbki tekstury bezpośrednio na kolor końcowych danych wyjściowych.

Przed rozpoczęciem upewnij się, że **właściwości** okna i **przybornika** są wyświetlane.

1.  Tworzenie modułu cieniującego DGSL chcesz pracować. Aby uzyskać informacje dotyczące sposobu dodawania modułu cieniującego DGSL do projektu, zobacz sekcję pierwsze kroki w [Shader Designer](../designers/shader-designer.md).

2.  Usuń **koloru punktu** węzła. W **wybierz** tryb, wybierz **koloru punktu** węzła, a następnie na pasku menu wybierz **Edytuj** > **Usuń**. To sprawia, że miejsce na węzeł, który zostanie dodany do następnego kroku.

3.  Dodaj **próbki tekstury** węzła do wykresu. W **przybornika**w obszarze **tekstury**, wybierz opcję **próbki tekstury** i przenieś go do powierzchni projektowej.

4.  Dodaj **koordynować tekstury** węzła do wykresu. W **przybornika**w obszarze **tekstury**, wybierz opcję **koordynować tekstury** i przenieś go do powierzchni projektowej.

5.  Wybierz teksturę do zastosowania. W **wybierz** tryb, wybierz **próbki tekstury** węzła, a następnie w polu **właściwości** okna, określ teksturę, która ma być za pomocą **nazwy pliku**  właściwości.

6.  Udostępnienie tekstury publicznie. Wybierz **próbki tekstury** węzła, a następnie w polu **właściwości** oknie **dostępu** właściwości **publicznych**. Teraz można ustawić tekstury z innego narzędzia, takie jak **edytora modelu**.

7.  Połącz się próbki tekstury z współrzędnych tekstury. W **wybierz** tryb, Przenieś **dane wyjściowe** terminali z **koordynować tekstury** węzeł, aby **UV** terminali z **tekstury Przykładowe** węzła. To połączenie pobiera próbki tekstury na określonych współrzędnych.

8.  Połącz się ostateczny kolor z próbki tekstury. Przenieś **RGB** terminali z **próbki tekstury** węzeł **RGB** terminali z **ostateczny kolor** węzeł, a następnie przenieść **Alfa** terminali z **próbki tekstury** węzeł **alfa** terminali z **ostateczny kolor** węzła.

Poniższej ilustracji ukończone programu do cieniowania programu graph i wersję zapoznawczą programu do cieniowania stosowane do modułu.

> [!NOTE]
> Na tej ilustracji płaszczyznę jest używany jako kształt (wersja zapoznawcza), a określono tekstury lepiej wykazać efekt programu do cieniowania.

![Wykres modułu cieniującego i podgląd efektów jej](../designers/media/digit-texture-effect.png)

Niektórych kształtów udostępniać lepsze wersje zapoznawcze niektórych programów do cieniowania. Aby uzyskać więcej informacji na temat programów do cieniowania w projektancie programu do cieniowania w wersji zapoznawczej, zobacz [Shader Designer](../designers/shader-designer.md)

## <a name="see-also"></a>Zobacz także

- [Instrukcje: stosowanie cieniowania do modelu 3D](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Edytor obrazów](../designers/image-editor.md)
- [Projektant cieniowania](../designers/shader-designer.md)
- [Węzły projektanta cieniowania](../designers/shader-designer-nodes.md)