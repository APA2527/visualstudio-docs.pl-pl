---
title: Jak utworzyć i stosowanie zasobów | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.XamlDesigner.CreateResource
- VS.XamlDesigner.EditResource
ms.assetid: 3ff4006d-659d-4073-9a41-06ff85e6cfdf
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75041cb9db00b48ea81dfe9a8639c41e4267262c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694282"
---
# <a name="how-to-create-and-apply-a-resource"></a>Jak utworzyć i stosowanie zasobów
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [sposób tworzenia i stosowanie zasobów](https://docs.microsoft.com/visualstudio/designers/how-to-create-and-apply-a-resource).  
  
Style i szablony dla elementów w Projektancie XAML są przechowywane w jednostkach wielokrotnego użytku, o nazwie zasoby. Style umożliwiają ustawianie właściwości elementu i ponownie użyć tych ustawień, aby uzyskać spójny wygląd między wieloma elementami. A [ControlTemplate](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.controltemplate.aspx) definiuje wygląd formantu i mogą być również stosowane jako zasób. Aby uzyskać więcej informacji, zobacz [Szybki Start: style formantów](http://go.microsoft.com/fwlink/?LinkID=248239) i [Szybki Start: kontrolowanie szablony](http://go.microsoft.com/fwlink/?LinkID=247982).  
  
 Zawsze, gdy tworzysz nowy zasób z istniejącej właściwości [styl](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.style.aspx), lub `ControlTemplate`, **Utwórz zasób** okno dialogowe pozwala na zdefiniowanie zasobu na poziomie aplikacji w poziomie dokumentu lub na poziomie elementu. Te poziomy określają, w którym może korzystać z zasobów. Na przykład jeśli zdefiniujesz zasób na poziomie elementu, zasób może być stosowane tylko do elementu, na którym został utworzony. Istnieje również możliwość przechowywania zasobu w słowniku zasobów, oddzielnym pliku, który można użyć ponownie w innym projekcie.  
  
### <a name="to-create-a-new-resource"></a>Aby utworzyć nowy zasób  
  
1.  Plik XAML jest otwarty w Projektancie XAML Utwórz element lub wybierz element w okno konspektu dokumentu.  
  
2.  W oknie dialogowym właściwości wybierz znacznik właściwości, która pojawia się jako symbol pole po prawej stronie wartości właściwości, a następnie wybierz **Konwertuj na nowy zasób**. Symbol białe pola wskazuje wartość domyślną, a symbol czarne pole zazwyczaj wskazuje, że zastosowano zasobu lokalnego  
  
     Pojawi się odpowiednie okno dialogowego dla tworzenia zasobu. To okno dialogowe pojawia się podczas tworzenia zasobu z pędzla:  
  
     ![Utwórz zasób — okno dialogowe](../designers/media/xaml-create-resource.png "xaml_create_resource")  
  
3.  W **nazwa (klucz)** wprowadź nazwę klucza. Jest to nazwa, do którego można użyć, jeśli chcesz, aby inne elementy, aby odwoływać się do zasobu.  
  
4.  W obszarze **zdefiniować w**, wybierz opcję określającą, którym ma być zdefiniowany zasób:  
  
    -   Aby udostępnić zasób do każdego dokumentu w aplikacji, wybierz opcję **aplikacji**.  
  
    -   Aby udostępnić zasób do bieżącego dokumentu, wybierz opcję **w tym dokumencie**.  
  
    -   Aby udostępnić zasób tylko element z której utworzono zasób lub jego elementy podrzędne, wybierz **w tym dokumencie**, a na liście rozwijanej wybierz *elementu*: *nazwy* .  
  
    -   Aby zdefiniować zasób w pliku słownika zasobów, które mogą zostać ponownie użyte w innych projektach, kliknij przycisk **słownik zasobów**, a następnie wybierz istniejący plik słownika zasobów, takich jak **StandardStyles.xaml**, na liście rozwijanej.  
  
5.  Wybierz **OK** przycisk, aby utworzyć zasób i zastosować go do elementu, z którego została utworzona.  
  
### <a name="to-apply-a-resource-to-an-element-or-property"></a>Aby zastosować zasób do elementu lub właściwości  
  
1.  Okno konspektu dokumentu wybierz element, który chcesz zastosować zasób.  
  
2.  Wykonaj jedną z następujących czynności:  
  
    -   Stosowanie zasobów do właściwości. W oknie dialogowym właściwości wybierz znacznik właściwości obok wartości właściwości, wybierz polecenie **zasobu lokalnego** lub **zasób systemowy**, a następnie wybierz zasób dostępny z wyświetlonej listy.  
  
         Jeśli nie widzisz zasobów, która powinna się pojawić, może to być, ponieważ typ zasobu nie jest zgodny z typem właściwości.  
  
    -   Stosowanie zasobu szablon stylu lub kontrolki do formantu. Otwórz menu kontekstowe dla formantu w oknie konspekt dokumentu, wybierz opcję **Edytuj szablon** lub **Edytuj dodatkowe szablony**, wybierz **Zastosuj zasób**, a następnie wybierz pozycję Nazwa szablonu kontrolki z wyświetlonej listy.  
  
        > [!NOTE]
        >  **Edytuj szablon** służy do stosowania szablonów kontrolek. **Edytuj dodatkowe szablony** służy do stosowania innego typu szablonu.  
  
     Zasoby mogą być stosowane wszędzie tam, gdzie są one zgodne. Na przykład, można zastosować do zasobu pędzla **pierwszego planu** właściwość <xref:Windows.UI.Xaml.Controls.TextBox> kontroli.  
  
### <a name="to-edit-a-resource"></a>Aby edytować zasobu  
  
1.  Wybierz element, w obszarze kompozycji lub w oknie konspekt dokumentu.  
  
2.  Wybierz znacznik właściwości domyślne lub lokalnych z prawej strony właściwości w oknie dialogowym właściwości, a następnie wybierz **Edytuj zasób** otworzyć **Edytuj zasób** okno dialogowe.  
  
3.  Modyfikowanie opcji dla zasobu.  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie interfejsu użytkownika przy użyciu projektanta XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)



