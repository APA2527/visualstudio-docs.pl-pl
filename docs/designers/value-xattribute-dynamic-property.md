---
title: Wartość (właściwość dynamiczna XAttribute)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c31179d33467f6be440882bce6f6cd9559d9a00
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080827"
---
# <a name="value-xattribute-dynamic-property"></a>Wartość (właściwość dynamiczna XAttribute)

Pobiera lub ustawia wartość atrybutu XML.

## <a name="syntax"></a>Składnia

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>Właściwość wartości/zwracana wartość

Element <xref:System.String> zawierający wartość tego atrybutu.

## <a name="exceptions"></a>Wyjątki

|Typ wyjątku|Warunek|
|--------------------|---------------|
|<xref:System.ArgumentNullException>|Podczas ustawiania, `value` jest `null`.|

## <a name="remarks"></a>Uwagi

Ta właściwość jest równoważna <xref:System.Xml.Linq.XAttribute.Value%2A> właściwość <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> klasy, ale ta właściwość dynamiczna obsługuje również powiadomienia o zmianach.

## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [Właściwości dynamiczne klasy XAttribute](../designers/xattribute-class-dynamic-properties.md)
- [Atrybut](../designers/attribute-xelement-dynamic-property.md)