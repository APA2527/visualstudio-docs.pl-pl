---
title: Element funkcji | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, Item functions
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 85dd03080a9dda58532d656161c3c44ae4943251
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081351"
---
# <a name="item-functions"></a>Funkcje elementów
Począwszy od programu MSBuild 4.0, kod w zadania i elementy docelowe można wywołać elementu funkcji, aby uzyskać informacje na temat elementów w projekcie. Te funkcje upraszczają pobierania elementów Distinct() i są szybsze niż elementy w pętli.  
  
## <a name="string-item-functions"></a>Ciąg funkcje elementów  
 Do działania na dowolną wartość elementu, można użyć właściwości i metod ciągów w programie .NET Framework. Aby uzyskać <xref:System.String> metod, określ nazwę metody. Aby uzyskać <xref:System.String> właściwości, określ nazwę właściwości, po przekroczeniu "rzeczoznawcy".  
  
 Elementy, które mają wiele ciągów ciąg metodę lub właściwość uruchamiane dla każdego ciągu.  
  
 Poniższy przykład pokazuje, jak używać tych funkcji element ciągu.  
  
```xml  
<ItemGroup>  
    <theItem Include="andromeda;tadpole;cartwheel" />  
</ItemGroup>  
  
<Target Name = "go">  
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />  
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />  
    <Message Text="Length   @(theItem->get_Length())" />  
    <Message Text="Chars    @(theItem->get_Chars(2))" />  
</Target>  
  
  <!--  
  Output:  
    IndexOf  3;-1;2  
    Replace  andromeda;pinwheel;cartwheel  
    Length   9;7;9  
    Chars    d;d;r  
  -->  
```  
  
## <a name="intrinsic-item-functions"></a>Funkcje wewnętrzne elementów  
 W tabeli poniżej wymieniono funkcje wewnętrzne dostępne dla elementów.  
  
|Funkcja|Przykład|Opis|  
|--------------|-------------|-----------------|  
|`Count`|`@(MyItem->Count())`|Zwraca liczbę elementów.|  
|`DirectoryName`|`@(MyItem->DirectoryName())`|Zwraca odpowiednik `Path.DirectoryName` dla każdego elementu.|  
|`Distinct`|`@(MyItem->Distinct())`|Zwraca elementy, które mają różne `Include` wartości. Metadanych jest ignorowany. Wynik porównania jest uwzględniana wielkość liter.|  
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|Zwraca elementy, które mają różne `itemspec` wartości. Metadanych jest ignorowany. Wynik porównania jest uwzględniana wielkość liter.|  
|`Reverse`|`@(MyItem->Reverse())`|Zwraca elementy w odwrotnej kolejności.|  
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|Zwraca `boolean` do wskazywania, czy dowolny element ma określonych metadanych nazwą i wartością. Wynik porównania jest uwzględniana wielkość liter.|  
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|Zwraca elementy z ich metadanymi wyczyszczone. Tylko `itemspec` są zachowywane.|  
|`HasMetadata`|`@(MyItem->HasMetadata("MetadataName"))`|Zwraca elementy, które mają taką nazwę określonych metadanych. Wynik porównania jest uwzględniana wielkość liter.|  
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|Zwraca wartości metadanych, których nazwa metadanych.|  
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue"))`|Zwraca elementy, które mają dane określone metadane nazwą i wartością. Wynik porównania jest uwzględniana wielkość liter.|  
  
 Poniższy przykład pokazuje, jak używać funkcji wewnętrznych elementów.  
  
```xml  
<ItemGroup>  
    <TheItem Include="first">  
        <Plant>geranium</Plant>  
    </TheItem>  
    <TheItem Include="second">  
        <Plant>algae</Plant>  
    </TheItem>  
    <TheItem Include="third">  
        <Plant>geranium</Plant>  
    </TheItem>  
</ItemGroup>  
  
<Target Name="go">  
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />  
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />  
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />  
    <Message Text=" " />  
    <Message Text="Count:   @(theItem->Count())" />  
    <Message Text="Reverse: @(theItem->Reverse())" />  
</Target>  
  
  <!--   
  Output:  
    MetaData:    geranium;algae;geranium  
    HasMetadata: first;second;third  
    WithMetadataValue: first;third  
  
    Count:   3  
    Reverse: third;second;first  
  -->  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Elementy](../msbuild/msbuild-items.md)
