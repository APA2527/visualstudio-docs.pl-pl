---
title: Opcje formatowania edytora U-SQL
description: Dowiedz się, jak za pomocą strony opcje formatowania i jej podstrony ustawić opcje formatowania kodu w edytorze kodu podczas programowania w języku U-SQL.
ms.custom: SEO-VS-2020
ms.date: 01/17/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.Spacing
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.NewLines
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.Indentation
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting
- VS.ToolsOptionsPages.Text_Editor.U-SQL.Formatting.General
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: a42fa7e5f40f413f7bc336ba8f0afbba7bdbf445
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99932296"
---
# <a name="options-text-editor-u-sql-formatting"></a>Opcje, Edytor tekstu, U-SQL, formatowanie

Na stronie opcje **formatowania** można ustawić opcje formatowania kodu w edytorze kodu. Aby uzyskać dostęp do tej strony opcji, wybierz pozycję **Narzędzia**  >  **Opcje**. W oknie dialogowym **Opcje** wybierz pozycję **Edytor tekstu**  >  **Formatowanie U-SQL**  >  .

## <a name="general-page"></a>Strona Ogólne

### <a name="general-settings"></a>Ustawienia ogólne

Te ustawienia mają wpływ na to, *kiedy* Edytor kodu stosuje opcje formatowania do kodu.

- **Automatycznie Formatuj ukończoną instrukcję przy wprowadzaniu średnika**

   Po wybraniu formatuje instrukcje w przypadku wybrania klucza średnika zgodnie z opcjami formatowania wybranymi dla edytora.

- **Automatycznie Formatuj przy wklejaniu**

   Gdy ta opcja jest zaznaczona, formatuje tekst wklejony do edytora, aby dopasować opcje formatowania wybrane dla edytora.

## <a name="preview-windows"></a>Okna wersji zapoznawczej

Podstrony **wcięcia**, **nowe wiersze** i **odstępy** są wyświetlane u dołu okna podglądu. Okno podglądu pokazuje efekt każdej opcji. Aby użyć okna podglądu, wybierz opcję formatowania. Okno podglądu zawiera przykład wybranej opcji. Gdy zmienisz ustawienie, zaznaczając pole wyboru, okno podglądu zostanie zaktualizowane, aby pokazać efekt nowego ustawienia.

### <a name="indentation-remarks"></a>Uwagi dotyczące wcięć

Opcje wcięć na stronach **kart** dla każdego języka określają, gdzie Edytor kodu umieszcza kursor po naciśnięciu klawisza **Enter** na końcu wiersza. Opcje wcięć w obszarze **Formatowanie** stosuje się, gdy kod jest formatowany automatycznie, na przykład:

- Podczas wklejania kodu do pliku, gdy jest zaznaczone **Automatyczne formatowanie przy wklejaniu**
- Gdy format jest formatowany ręcznie

## <a name="see-also"></a>Zobacz też

- [Ogólne, środowisko, Opcje — okno dialogowe](../../ide/reference/general-environment-options-dialog-box.md)
