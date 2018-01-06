---
title: Rejestrowanie VSPackages | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 119e6dc088c6f6e80d79ab096d97b7404c530611
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="registering-vspackages"></a>Rejestrowanie VSPackages
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]zależy od plików .pkgdef do opisu i zlokalizuj pakiet VSPackage. Plik .pkgdef zawiera wszystkie informacje rejestracyjne, które w przeciwnym razie zostanie dodany do rejestru systemowego. Zarządzane VSPackages są rejestrowane przez dodanie atrybutów do kodu źródłowego, a następnie uruchamiając [elementu CreatePkgDef narzędzie](../../extensibility/internals/createpkgdef-utility.md) na zestaw wynikowy do wygenerowania pliku .pkgdef.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Określanie lokalizacji pliku pakietu VSPackage dla powłoki VS Shell](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)  
 Opisuje ścieżki ładowania VSPackages.  
  
 [Rejestrowanie i wyrejestrowywanie pakietów VSPackage](../../extensibility/registering-and-unregistering-vspackages.md)  
 Wyjaśniono, jak zarejestrować pakiet VSPackage.  
