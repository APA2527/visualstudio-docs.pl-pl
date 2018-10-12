---
title: Właściwości ról w domenie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7bb18c-638e-45e8-9d79-9aa6a9e14b0e
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 51149979544c19b0a887ad77e80a26284051778b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49244091"
---
# <a name="properties-of-domain-roles"></a>Właściwości ról w domenie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

W poniższej tabeli przedstawiono właściwości są skojarzone z rolą domeny. Aby uzyskać informacji na temat ról w domenie, zobacz [objaśnienie modeli, klas i relacji](../modeling/understanding-models-classes-and-relationships.md). Aby uzyskać więcej informacji o tym, jak korzystać z tych właściwości, zobacz [dostosowywanie i rozszerzanie języka specyficznego dla domeny](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Właściwość|Opis|Domyślny|  
|--------------|-----------------|-------------|  
|Typ kolekcji|Jeśli ta rola ma liczebność 0.. * lub 1.. \*, ta właściwość dostosowuje typ ogólny, który jest używany do przechowywania kolekcji łącza.|`(none)` - <xref:Microsoft.VisualStudio.Modeling.LinkedElementCollection%601> jest używana|  
|Atrybuty niestandardowe|Atrybuty, które są określone w tym miejscu zostaną dodane jako atrybuty do klasy wygenerowanego kodu.|\<Brak >|  
|Właściwość jest możliwa do przeglądania|Jeśli `True`, a Jeśli liczebność relacji jest od 0 do 1 lub 1.. 1, właściwości roli może być przeglądany przez użytkownika w **właściwości** okna. Właściwość Wyświetla nazwę elementu na drugim końcu łącza relacji.|`True`|  
|Jest Generator właściwości|Jeśli `True`, właściwości roli jest generowany dla tej roli, co umożliwia przenoszenie relacji w kodzie programu. Możesz ustawić wartość false, mogą przechodzić zależności w mniej skuteczny sposób, przy użyciu metod statycznych relacji domeny.|`True`|  
|Modyfikator dostępu metody pobierającej właściwości|Modyfikator dostępu dla metody pobierającej wygenerowanej właściwości (`public`, `internal`, `private`, `protected`, lub `protected internal`).|`public`|  
|Modyfikator dostępu metody ustawiającej właściwość|Modyfikator dostępu dla metody ustawiającej wygenerowanej właściwości (`public`, `internal`, `private`, `protected`, lub `protected internal`).|`public`|  
|Liczebność|Liczba elementów modelu, które mogą pełnić rolę odwrotną (`0..1`, `1..1`, `0..*`, lub `1..*`). Jeśli liczebność jest `0..*` lub `1..*`, następnie wygenerowana właściwość reprezentuje kolekcję; w przeciwnym razie wygenerowana właściwość reprezentuje element pojedynczego modelu.|Zależy od typu relacji i tego, czy jest to rola źródłowa lub docelowa w relacji.|  
|Nazwa|Nazwa roli domeny. Ta właściwość nie może zawierać spacji.|Nazwa klasy domeny obiektu pełniącego rolę dla tej roli.|  
|Propaguje kopiowania|`DoNotPropagateCopy` -Kopiowanego obiektu pełniącego rolę będzie żadnej kopii tego łącza.<br /><br /> `PropagateCopyToLinkOnly` -Skopiowany link wskazuje na istniejący obiekt pełniący rolę odwrotną.<br /><br /> `PropagateCopyToLinkAndOppositeRolePlayer` -Skopiowany link wskazuje kopię obiektu pełniącego rolę odwrotną.|`PropagateCopyToLinkAndOppositeRolePlayer` dla ról źródło osadzenia.<br /><br /> `DoNotPropagateCopy` dla innych ról.<br /><br /> Aby uzyskać więcej informacji, zobacz [Dostosowywanie zachowania dotyczącego kopiowania](../modeling/customizing-copy-behavior.md)|  
|Propaguje Delete|`True` Aby usunąć element, który odgrywa tej roli, gdy skojarzone łącze zostało usunięte.|`True` dla elementu docelowego osadzania roli.<br /><br /> `False` dla innych ról.<br /><br /> Aby uzyskać więcej informacji, zobacz [Dostosowywanie zachowania dotyczącego usuwania](../modeling/customizing-deletion-behavior.md).|  
|Nazwa właściwości|Nazwa właściwości wygenerowanej w kodzie obiektu pełniącego rolę. Ta nazwa nie może zawierać białych znaków.|Nazwa roli odwrotną, jeśli ta rola ma wartość zero do jednego lub jeden do jednego liczebność; w przeciwnym razie nazwa pluralized rolę odwrotną.|  
|Obiekt pełniący rolę|Klasa domeny element, który można odtworzyć tę rolę w relacji. Ta właściwość jest tylko do odczytu.|Klasa domeny obiektu pełniącego rolę dla tej roli.|  
|Uwagi|Uwagi informacyjne skojarzone z rolą domeny.|\<Brak >|  
|Kategoria|Kategoria, pod którą wygenerowana właściwość pojawia się w **właściwości** okna w wygenerowanym projektancie. Jeśli ta właściwość jest pusta, a następnie wygenerowana właściwość pojawia się w obszarze **różne** kategorii|\<Brak >|  
|Opis|Opis, który jest używany do dokumentowania kodu i jest używany w Interfejsie użytkownika wygenerowanego projektanta.<br /><br /> Opis jest wyświetlany w etykietce narzędzia funkcji Intellisense dla właściwości wygenerowanej klasy obiektu pełniącego rolę.|`Description for` *Pełna nazwa roli*|  
|Nazwa wyświetlana|Nazwa która jest wyświetlana w wygenerowanym projektancie dla roli domeny.|Skorygowaną wartość właściwości Name.|  
|Słowo kluczowe pomocy|Opcjonalne słowo kluczowe, które jest używane do indeksowania pomocy F1 dla okna rolę domeny.|\<Brak >|  
|Wyświetlana nazwa właściwości|Nazwa która jest wyświetlana w wygenerowanym projektancie dla właściwości wygenerowanej roli.|Skorygowaną wartość właściwości nazwy właściwości.|  
  
> [!NOTE]
>  Wartością domyślną nazwę wyświetlaną opiera się na wartości właściwości skojarzonej, wstawiając spacje przed znakiem każdego wielkie litery, który jest poprzedzony znakiem małe i który nie następuje inny znak wielkie litery.  
  
## <a name="see-also"></a>Zobacz też  
 [Właściwości relacji domeny](../modeling/properties-of-domain-relationships.md)



