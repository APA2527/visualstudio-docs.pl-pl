---
title: Resolvekeysource — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 548fd2182292d9e7fdeac59d09dab2977c351d0b
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39155532"
---
# <a name="resolvekeysource-task"></a>ResolveKeySource — zadanie
Określa źródło klucza silnej nazwy.  
  
## <a name="task-parameters"></a>Parametry zadania  
 W poniższej tabeli opisano parametry `ResolveKeySource` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`AutoClosePasswordPromptShow`|Opcjonalnie `Int32` parametru.<br /><br /> Pobiera lub ustawia czas, w ciągu kilku sekund, aby wyświetlić liczbę w dół wiadomości.|  
|`AutoClosePasswordPromptTimeout`|Opcjonalnie `Int32` parametru.<br /><br /> Pobiera lub ustawia czas, w ciągu kilku sekund oczekiwania przed zamknięciem okna dialogowego monitu hasła.|  
|`CertificateFile`|Opcjonalnie `String` parametru.<br /><br /> Pobiera lub ustawia ścieżkę do pliku certyfikatu.|  
|`CertificateThumbprint`|Opcjonalnie `String` parametru.<br /><br /> Pobiera lub ustawia odcisk palca certyfikatu.|  
|`KeyFile`|Opcjonalnie `String` parametru.<br /><br /> Pobiera lub ustawia ścieżkę pliku klucza.|  
|`ResolvedKeyContainer`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Pobiera lub ustawia rozwiązane kontener kluczy.|  
|`ResolvedKeyFile`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Pobiera lub ustawia rozpoznać pliku klucza.|  
|`ResolvedThumbprint`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Pobiera lub ustawia odcisk palca certyfikatu rozwiązane.|  
|`ShowImportDialogDespitePreviousFailures`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli `true`, Pokaż Importuj okno dialogowe, niezależnie od wcześniejszych niepowodzeń.|  
|`SuppressAutoClosePasswordPrompt`|Opcjonalnie `Boolean` parametru.<br /><br /> Pobiera lub ustawia wartość logiczną, która określa, czy okno dialogowe monitu hasła powinna nie automatycznego zamykania.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)