---
title: schematy XML
description: Dowiedz się więcej o oknie dialogowym schematy XML, które służy do wybierania schematów języka definicji schematu XML (XSD) do skojarzenia z dokumentem XML.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.xmleditor.schemasdialog
ms.assetid: 0271fa26-2205-49bd-96e0-ae1441571808
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 1c91e97d0508ab85893409386ddd3ab9dded7f45
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99874838"
---
# <a name="xml-schemas-dialog-box"></a>Schematy XML, okno dialogowe

Okno dialogowe **schematy XML** służy do wybierania schematu definicji języka (XSD) XML do skojarzenia z dokumentem XML. Można wybrać schemat z pamięci podręcznej schematów lub określić schemat, który nie znajduje się w pamięci podręcznej. Wybrane schematy są uważane za część zestawu schematów. Zestaw schematu jest używany na potrzeby funkcji IntelliSense, a także do sprawdzania poprawności dokumentu XML.

Możesz uzyskać dostęp do okna dialogowego **schematy XML** , klikając przycisk **schematy** w oknie właściwości dokumentu lub wybierając **schematy** z menu **XML** .

## <a name="uielement-list"></a>Lista elementów UI

**Zastosowanie**

Wybierz, jak schemat XML ma być używany.

- **Automatyczny**. Ten schemat nie jest używany przez bieżący dokument, ale jest dostępny do automatycznego kojarzenia. Jeśli dokument XML deklaruje przestrzeń nazw zgodną `targetNamespace` z tym schematem, schemat zostanie automatycznie skojarzony i zostanie uwzględniony w zestawie schematów.

- **Użyj tego schematu**. Ten schemat jest używany przez bieżący dokument. Użytkownik jawnie zażądał użycia tego schematu przez kliknięcie tej kolumny lub schemat został automatycznie skojarzony na podstawie pasującego elementu `targetNamespace` .

- **Nie używaj wybranych schematów**. Ten schemat nie jest używany przez bieżący dokument, nawet jeśli schemat ma pasujący element `targetNamespace` . To ustawienie może być przydatne do rozwiązywania konfliktów, jeśli istnieje więcej niż jedna wersja tego samego schematu w pamięci podręcznej schematów lub w rozwiązaniu.

**Docelowa przestrzeń nazw**

Wyświetla docelową przestrzeń nazw skojarzoną ze schematem XML.

**Nazwa pliku**

Wyświetla nazwę pliku schematu XML.

**Dodaj**

Otwiera okno dialogowe **otwieranie schematu XSD** , które umożliwia wybranie dodatkowych schematów do dodania do zestawu schematów. Po dodaniu schematu do zestawu schematów wartość **opcji Użyj** kolumny jest ustawiana na **Użyj tego schematu**.

**Usuń**

Usuwa aktualnie wybrany schemat z zestawu schematów. Spowoduje to usunięcie schematu z pamięci podręcznej schematu w pamięci, ale nie z systemu plików.

## <a name="see-also"></a>Zobacz też

- [Instrukcje: Wybieranie schematów XML do użycia](../xml-tools/how-to-select-the-xml-schemas-to-use.md)
- [Pamięć podręczna schematów](../xml-tools/schema-cache.md)
