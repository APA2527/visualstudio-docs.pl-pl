---
title: Fragmenty kodu XML
description: Dowiedz się więcej o funkcji fragmentów kodu XML w edytorze XML, która umożliwia szybsze tworzenie plików XML przez ponowne używanie fragmentów kodu XML i wstawianie ich do plików.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 158f51ddc8db8f83d98c34aa03b3ee4f5a1a4d01
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99874824"
---
# <a name="xml-snippets"></a>Fragmenty kodu XML

Edytor XML oferuje funkcję, nazywaną *fragmentami kodu XML*, która umożliwia szybsze tworzenie plików XML. Można ponownie użyć fragmentów kodu XML, wstawiając je do plików. Możesz również generować dane XML na podstawie schematu definicji schematu XML (XSD).

## <a name="reusable-xml-snippets"></a>Fragmenty kodu XML wielokrotnego użytku

Edytor XML zawiera wiele fragmentów kodu, które obejmują niektóre typowe zadania. Dzięki temu można łatwiej tworzyć pliki XML. Na przykład jeśli tworzysz schemat XML przy użyciu fragmentów "element sekwencji typu złożonego" i "element typu prostego", wstawi następujący tekst XML do pliku. Następnie należy zmienić `name` wartość tak, aby odpowiadała Twoim potrzebom.

```xml
<xs:element name="name">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="name">
        <xs:simpleType>
          <xs:restriction base="xs:string"></xs:restriction>
        </xs:simpleType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

Fragmenty kodu można wstawiać na dwa sposoby. Polecenie **Wstaw fragment** kodu wstawia fragment kodu XML w pozycji kursora. Element **przestrzenny z** poleceniem otacza fragment kodu XML wokół zaznaczonego tekstu. Oba polecenia są dostępne w podmenu **IntelliSense** w menu **Edycja** lub w menu po kliknięciu prawym przyciskiem myszy w edytorze.

Aby uzyskać więcej informacji, zobacz [How to: Use XML defragments](../xml-tools/how-to-use-xml-snippets.md).

## <a name="schema-generated-xml-snippets"></a>Fragmenty kodu XML generowane przez schemat

Edytor XML umożliwia również generowanie fragmentu kodu XML na podstawie schematu XML. Ta funkcja umożliwia wypełnienie elementu elementami XML wygenerowanymi na podstawie informacji o schemacie dla tego elementu. Aby uzyskać więcej informacji, zobacz [jak: generować fragment kodu XML ze schematu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md).

## <a name="create-new-xml-snippets"></a>Utwórz nowe fragmenty kodu XML

Oprócz fragmentów kodu, które są domyślnie dołączone do programu Visual Studio, można również tworzyć własne fragmenty kodu XML i korzystać z nich. Aby uzyskać więcej informacji, zobacz [How to: Create XML defragments](../xml-tools/how-to-create-xml-snippets.md).

## <a name="see-also"></a>Zobacz też

- [Fragmenty kodu w programie Visual Studio](../ide/code-snippets.md)
- [Edytor XML](../xml-tools/xml-editor.md)
