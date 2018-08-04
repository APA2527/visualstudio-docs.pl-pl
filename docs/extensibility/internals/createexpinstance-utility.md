---
title: Narzędzie CreateExpInstance | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a0f7f52f45023106d3e504258a538823c1c8fbb4
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39500660"
---
# <a name="createexpinstance-utility"></a>Narzędzie CreateExpInstance
Użyj **CreateExpInstance** narzędzie do tworzenia, zresetuj lub Usuń wystąpienie doświadczalne programu Visual Studio. Wystąpienie eksperymentalne umożliwia debugowanie i testowanie rozszerzenia programu Visual Studio bez zmiany podstawowego produktu.  
  
## <a name="syntax"></a>Składnia  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
## <a name="parameters"></a>Parametry  
 **/ Tworzenie** tworzy wystąpienie eksperymentalne.  
  
 **/ Reset**  
 Usuwa wystąpienie eksperymentalne programu, a następnie tworzy nową.  
  
 **/ Clean**  
 Usuwa wystąpienie eksperymentalne.  
  
 **/ VSInstance**  
 Nazwa katalogu, który zawiera wystąpienie programu Visual Studio w podstawowej, aby skopiować.  
  
 **/ RootSuffix**  
 Sufiks, który można dołączyć do nazwy katalogu, w eksperymentalnym wystąpieniu.  
  
## <a name="remarks"></a>Uwagi  
 Podczas pracy w rozszerzeniu Visual Studio, można nacisnąć F5, aby otworzyć domyślne wystąpienie doświadczalne i zainstaluj rozszerzenie bieżącego. Jeśli żadne wystąpienie doświadczalne jest dostępny, program Visual Studio tworzy jeden, który zawiera ustawienia domyślne.  
  
 Domyślna lokalizacja wystąpienie doświadczalne zależy od numeru wersji programu Visual Studio. Na przykład dla programu Visual Studio 2015, lokalizacja jest *%localappdata%\Microsoft\VisualStudio\14.0Exp\\*. Wszystkie pliki w lokalizacji katalogu są traktowane jako część tego wystąpienia. Wszelkie dodatkowe wystąpienia doświadczalnego nie zostanie załadowany przez program Visual Studio, chyba, że nazwa katalogu jest zmieniana na lokalizację domyślną.  
  
 Program Visual Studio nie uzyskać dostępu do rejestru systemowego, po otwarciu wystąpienie eksperymentalne. Różni się to z wcześniejszych wersji programu Visual Studio, które są używane w wersji doświadczalnej gałęzi rejestru.  
  
 **CreateExpInstance** zastępuje narzędzie **VsRegEx** narzędzia.  
  
 Poniższy przykład Resetuje domyślne doświadczalnym wystąpieniu programu Visual Studio:  
  
 **/VSInstance CreateExpInstance.exe/reset = 14.0 /RootSuffix = Exp**  
  
## <a name="see-also"></a>Zobacz także  
 [Pakiety VSPackage](../../extensibility/internals/vspackages.md)