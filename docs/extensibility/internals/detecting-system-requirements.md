---
title: Wykrywanie wymagań systemowych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- setup, VSPackages
- launch conditions
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a794391001934164e52bdd73d940cb73ff3b5f3b
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39500085"
---
# <a name="detect-system-requirements"></a>Wykrywanie wymagań systemowych
Pakietu VSPackage nie może działać, jeśli nie zainstalowano programu Visual Studio. Gdy Instalator systemu Microsoft Windows umożliwia zarządzanie instalacjami Twojego pakietu VSPackage, można skonfigurować Instalatora aby wykryć, czy jest zainstalowany program Visual Studio. Można również skonfigurować ją do sprawdzania systemu pod kątem innych wymagań, na przykład konkretnej wersji systemu Windows lub określoną ilość pamięci RAM.  
  
## <a name="detect-visual-studio-editions"></a>Wykryć wersji programu Visual Studio  
 Aby ustalić, czy jest zainstalowana wersja programu Visual Studio, upewnij się, że wartość **zainstalować** klucz rejestru jest *(REG_DWORD) 1* w odpowiednim folderze, wymienione w poniższej tabeli. Zwróć uwagę, że hierarchia wersje programu Visual Studio:  
  
1.  Enterprise  
  
2.  Professional Edition  
  
3.  Społeczność  
      
Nowsza wersja jest zainstalowana, klucze rejestru, w przypadku tej wersji są dodawane również jak w przypadku starszych wersji. Oznacza to, jeśli jest zainstalowany w wersji Enterprise, **zainstalować** jest ustawiona na *1* dla przedsiębiorstw, a także wersje Professional i społeczności. W związku z tym należy sprawdzić tylko w przypadku najnowszej wersji, których potrzebujesz.  
  
> [!NOTE]
>  W 64-bitową wersję Edytora rejestru w 32-bitowe klucze są wyświetlane w obszarze **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\\**. Klucze programu Visual Studio, podlegają **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing\\**.  
  
|Produkt|Key|  
|-------------|---------|  
|Visual Studio Enterprise 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\enterprise|  
|Visual Studio Professional 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\professional|  
|Visual Studio Community 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\community|  
|Visual Studio 2015 Shell (integrated i isolated)|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell|  
  
## <a name="detect-when-visual-studio-is-running"></a>Wykryj, kiedy program Visual Studio jest uruchomiony.  
 Nie można zarejestrować poprawnie Twojego pakietu VSPackage, jeśli program Visual Studio jest uruchomiony podczas instalowania pakietu VSPackage. Instalator musi wykryć, kiedy program Visual Studio jest uruchomiony i następnie odmówić zainstalować ten program. Instalator Windows nie pozwalają używać wpisów tabeli, aby umożliwić wykrywanie takich modyfikacji. Zamiast tego Utwórz akcję niestandardową, w następujący sposób: Użyj `EnumProcesses` funkcję, aby wykryć *devenv.exe* przetwarzania, a następnie ustawić właściwości Instalatora, który jest używany w stanie uruchomienia lub warunkowo wyświetlane jest okno dialogowe który monituje użytkownika o Zamknij program Visual Studio.  
  
## <a name="see-also"></a>Zobacz także  
 [Instalowanie pakietów VSPackage przy użyciu Instalatora Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)