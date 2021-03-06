---
title: Użytkownik (VSPerfCmd) | Microsoft Docs
description: Dowiedz się, jak opcja użytkownik określa domenę i nazwę użytkownika konta, które jest właścicielem profilowanego procesu.
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ee1a478e-374d-4f30-ae28-d260b9d4723a
author: mikejo5000
ms.author: mikejo
manager: jmartens
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: b0240a4dcf0830dca6667bcbd055d677ef7bc204
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99886005"
---
# <a name="user-vsperfcmd"></a>Użytkownik (VSPerfCmd)
Opcja **użytkownik** określa domenę i nazwę użytkownika konta, które jest właścicielem profilowanego procesu. Ta opcja jest wymagana tylko wtedy, gdy proces działa jako użytkownik inny niż zalogowany użytkownik. Właściciel procesu jest wymieniony w kolumnie Nazwa użytkownika na karcie **procesy** w Menedżerze zadań systemu Windows.

 Opcję **użytkownika** można określić tylko w wierszu polecenia, który zawiera również opcję **Start** .

## <a name="syntax"></a>Składnia

```cmd
VSPerfCmd.exe /Start:Method /Output:FileName /User:[Domain\]UserName [Options]
```

#### <a name="parameters"></a>Parametry
 `Domain` Nazwa domeny użytkownika.

 `UserName` Nazwa użytkownika.

## <a name="required-options"></a>Wymagane opcje
 Opcji **użytkownika** można używać tylko z opcją **Start** .

 **Rozpocznij:** `Method` Inicjuje Profiler do określonej metody profilowania.

## <a name="example"></a>Przykład
 Poniższy przykład demonstruje użycie opcji **użytkownika** .

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /User:SYSTEM
```

## <a name="see-also"></a>Zobacz też
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profile aplikacji autonomicznych](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profilowanie aplikacji sieci Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Usługi profilu](../profiling/command-line-profiling-of-services.md)
