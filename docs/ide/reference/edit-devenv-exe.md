---
title: -Edit (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv switch
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c8ee96ef2cd8713b592eabef11942e895bd93534
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39510133"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
Otwiera określony plik w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Składnia

```cmd
Devenv /edit [file1[ file2]]
```

## <a name="arguments"></a>Argumenty
 `file1`

 Opcjonalna. Plik aby otworzyć w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Jeśli żadne wystąpienie elementu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] istnieje, jest tworzone nowe wystąpienie o uproszczonym układzie okna, a `file1` jest otwarty w nowym wystąpieniu.

 `file2`

 Opcjonalna. Jeden lub więcej dodatkowych plików do otwierania w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="remarks"></a>Uwagi
 Jeśli plik nie jest określony, a istniejącego wystąpienia programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], istniejące wystąpienie programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zostanie ustawiony fokus. Jeśli plik nie jest określona i nie żadne istniejące wystąpienie [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], nowe wystąpienie klasy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] jest tworzona przy użyciu uproszczonym układzie okna.

 Jeśli istniejące wystąpienie programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] jest w stanie modalne, na przykład, jeśli [okno dialogowe Opcje](../../ide/reference/options-dialog-box-visual-studio.md) jest otwarty, będzie plik open w istniejącym wystąpieniu kiedy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kończy stan modalny.

## <a name="example"></a>Przykład
 W tym przykładzie otwiera plik `MyFile.cs` w istniejącym wystąpieniu programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] lub otwiera plik w nowym wystąpieniu programu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Jeśli już nie istnieje.

```cmd
devenv /edit MyFile.cs
```

## <a name="see-also"></a>Zobacz też

- [Przełączniki wiersza polecenia Devenv](../../ide/reference/devenv-command-line-switches.md)