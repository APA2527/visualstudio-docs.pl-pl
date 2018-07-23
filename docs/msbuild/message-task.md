---
title: Komunikat zadania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Message
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Message task
- Message task [MSBuild]
ms.assetid: 2293309d-42b6-46dc-9684-8c146f66bc28
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0b61bf9def1ba37667302850527715eed1db4ff
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178335"
---
# <a name="message-task"></a>Komunikat — Zadanie
Rejestruje komunikat podczas kompilacji.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `Message` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`Importance`|Opcjonalnie `String` parametru.<br /><br /> Określa ważność wiadomości. Ten parametr może mieć wartość `high`, `normal` lub `low`. Wartość domyślna to `normal`.|  
|`Text`|Opcjonalnie `String` parametru.<br /><br /> Tekst błędu logowania.|  
  
## <a name="remarks"></a>Uwagi  
 `Message` Zadanie pozwala [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty do problemu komunikatów rejestratorów w innych czynności w procesie kompilacji.  
  
 Jeśli `Condition` daje w wyniku parametr `true`, wartość `Text` parametru będą rejestrowane i kompilacja będą w dalszym ciągu wykonują. Jeśli `Condition` parametr nie istnieje, tekst komunikatu jest rejestrowane. Aby uzyskać więcej informacji na temat rejestrowania, zobacz [dzienniki kompilacji Uzyskaj](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Domyślnie komunikat jest wysyłany do rejestratora konsoli do programu MSBuild. Można to zmienić, ustawiając <xref:Microsoft.Build.Tasks.TaskExtension.Log%2A> parametru. Rejestrator interpretuje `Importance` parametru.  
  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu rejestruje komunikaty wszystkich rejestratorów zarejestrowanych.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="DisplayMessages">  
        <Message Text="Project File Name = $(MSBuildProjectFile)" />  
        <Message Text="Project Extension = $(MSBuildProjectExtension)" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Uzyskiwanie dzienników kompilacji](../msbuild/obtaining-build-logs-with-msbuild.md)