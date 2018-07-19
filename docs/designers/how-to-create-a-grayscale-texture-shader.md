---
title: 'Porady: tworzenie cieniowania tekstury skali szarości'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 79181d81-44af-445e-9a18-03483dd70260
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c1910926c6cb2d181f4e5e24ffb1bc1c75a56b3
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924190"
---
# <a name="how-to-create-a-grayscale-texture-shader"></a>Porady: tworzenie cieniowania tekstury skali szarości

W tym artykule przedstawiono sposób użycia języka programu do cieniowania wykres kierowany (DGSL) i Projektant programu do cieniowania do tworzenie cieniowania tekstury skali szarości. Ten program do cieniowania Modyfikuje wartość koloru RGB próbki tekstury, a następnie używa go wraz z zostały zmodyfikowane wartości alfa, można ustawić ostateczny kolor.

## <a name="create-a-grayscale-texture-shader"></a>Tworzenie cieniowania tekstury skali szarości

Przed napisaniem kolor końcowych danych wyjściowych, zmieniając wartość koloru próbki tekstury, można zaimplementować cieniowania tekstury skali szarości.

Przed rozpoczęciem upewnij się, że **właściwości** okna i **przybornika** są wyświetlane.

1.  Tworzenie cieniowania tekstury podstawowej, zgodnie z opisem w [porady: tworzenie cieniowania tekstury podstawowej](../designers/how-to-create-a-basic-texture-shader.md).

2.  Odłącz **RGB** terminali z **próbki tekstury** węzła z **RGB** terminali z **ostateczny kolor** węzła. W **wybierz** trybie wybierz **RGB** terminali z **próbki tekstury** węzła, a następnie wybierz **Przerwij linki**. To sprawia, że miejsce na węzeł, który zostanie dodany do następnego kroku.

3.  Dodaj **polecenie Zmniejsz nasycenie** węzła do wykresu. W **przybornika**w obszarze **filtry**, wybierz opcję **polecenie Zmniejsz nasycenie** i przenieś go do powierzchni projektowej.

4.  Oblicz wartość skali szarości przy użyciu **polecenie Zmniejsz nasycenie** węzła. W **wybierz** tryb, Przenieś **RGB** terminali z **próbki tekstury** węzeł **RGB** terminali z **polecenie Zmniejsz nasycenie**  węzła.

    > [!NOTE]
    > Domyślnie **polecenie Zmniejsz nasycenie** węzła pełni desaturates koloru okna wprowadzania i wykorzystuje wagi jasności standardowych konwersji na odcienie szarości. Możesz zmienić sposób, w jaki **polecenie Zmniejsz nasycenie** węzeł, który zachowuje się, zmieniając wartość **jasności** właściwości lub tylko częściowo desaturating koloru okna wprowadzania. Aby częściowo Zmniejsz nasycenie koloru okna wprowadzania, należy podać wartość skalarną w zakresie [0,1) do **procent** terminali z **polecenie Zmniejsz nasycenie** węzła.

5.  Połącz się ostateczny kolor z wartości koloru skali szarości. Przenieś **dane wyjściowe** terminali z **polecenie Zmniejsz nasycenie** węzeł **RGB** terminali z **ostateczny kolor** węzła.

Poniższej ilustracji ukończone programu do cieniowania programu graph i wersję zapoznawczą programu do cieniowania stosowane do modułu.

> [!NOTE]
> Na tej ilustracji płaszczyznę jest używany jako kształt (wersja zapoznawcza), a określono tekstury lepiej wykazać efekt programu do cieniowania.

![Wykres modułu cieniującego i podgląd efektów jej](../designers/media/digit-grayscale-effect.png)

Niektórych kształtów udostępniać lepsze wersje zapoznawcze niektórych programów do cieniowania. Aby uzyskać więcej informacji na temat programów do cieniowania w projektancie programu do cieniowania udostępnia w wersji zapoznawczej, zobacz [Shader Designer](../designers/shader-designer.md)

## <a name="see-also"></a>Zobacz także

- [Instrukcje: stosowanie cieniowania do modelu 3D](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Instrukcje: eksportowanie cieniowania](../designers/how-to-export-a-shader.md)
- [Edytor obrazów](../designers/image-editor.md)
- [Projektant cieniowania](../designers/shader-designer.md)
- [Węzły projektanta cieniowania](../designers/shader-designer-nodes.md)