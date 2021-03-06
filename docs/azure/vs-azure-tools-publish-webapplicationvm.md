---
title: Publish-WebApplicationVM | Microsoft Docs
description: Dowiedz się, jak wdrożyć aplikację sieci Web na maszynie wirtualnej. Ten skrypt tworzy wymagane zasoby w subskrypcji platformy Azure, jeśli nie istnieją.
author: ghogen
manager: jmartens
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: 6bd9659adec2d1d88a7a02c7985fc0f823c5d811
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99844011"
---
# <a name="publish-webapplicationvm-windows-powershell-script"></a>Publish-WebApplicationVM (skrypt programu Windows PowerShell)
Wdraża aplikację sieci Web na maszynie wirtualnej. Skrypt tworzy wymagane zasoby w subskrypcji platformy Azure, jeśli nie istnieją.

```
Publish-WebApplicationVM
–Configuration <configuration>
-SubscriptionName <subscriptionName>
-WebDeployPackage <packageName>
-VMPassword @{Name = "name"; Password = "password")
-DatabaseServerPassword @{Name = "name"; Password = "password"}
-SendHostMessagesToOutput
-Verbose
```

### <a name="configuration"></a>Konfigurowanie
Ścieżka do pliku konfiguracji JSON opisującego Szczegóły wdrożenia.

| Aliasy | brak |
| --- | --- |
| Wymagane? |true |
| Położenie |nazwane |
| Wartość domyślna |brak |
| Akceptujesz dane wejściowe potoku? |fałsz |
| Akceptować symbole wieloznaczne? |fałsz |

### <a name="subscriptionname"></a>SubscriptionName
Nazwa subskrypcji platformy Azure, w której chcesz utworzyć maszynę wirtualną.

| Aliasy | brak |
| --- | --- |
| Wymagane? |fałsz |
| Położenie |nazwane |
| Wartość domyślna |Używa pierwszej subskrypcji w pliku subskrypcji |
| Akceptujesz dane wejściowe potoku? |fałsz |
| Akceptować symbole wieloznaczne? |fałsz |

### <a name="webdeploypackage"></a>Webdeploypackage została
Ścieżka do pakietu wdrożeniowego sieci Web, która ma zostać opublikowana na maszynie wirtualnej. Ten pakiet można utworzyć przy użyciu Kreatora publikacji w sieci Web w programie Visual Studio. Zobacz [jak: Tworzenie pakietu wdrożeniowego sieci Web w programie Visual Studio](/previous-versions/aspnet/dd465323(v=vs.110)).

| Aliasy | brak |
| --- | --- |
| Wymagane? |fałsz |
| Położenie |nazwane |
| Wartość domyślna |brak |
| Akceptujesz dane wejściowe potoku? |fałsz |
| Akceptować symbole wieloznaczne? |fałsz |

### <a name="allowuntrusted"></a>AllowUntrusted
W przypadku wartości true Zezwalaj na korzystanie z certyfikatów, które nie są podpisane przez zaufany główny urząd certyfikacji.

| Aliasy | brak |
| --- | --- |
| Wymagane? |fałsz |
| Położenie |nazwane |
| Wartość domyślna |fałsz |
| Akceptujesz dane wejściowe potoku? |fałsz |
| Akceptować symbole wieloznaczne? |fałsz |

### <a name="vmpassword"></a>VMPassword
Poświadczenia dla konta maszyny wirtualnej. Przykład:-VMPassword @ {Name = "admin"; Hasło = "hasło"}

| Aliasy | brak |
| --- | --- |
| Wymagane? |fałsz |
| Położenie |nazwane |
| Wartość domyślna |brak |
| Akceptujesz dane wejściowe potoku? |fałsz |
| Akceptować symbole wieloznaczne? |fałsz |

### <a name="databaseserverpassword"></a>DatabaseServerPassword
Poświadczenia dla bazy danych SQL na platformie Azure. Przykład:-DatabaseServerPassword @ {Name = "admin"; Hasło = "hasło"}

| Aliasy | brak |
| --- | --- |
| Wymagane? |fałsz |
| Położenie |nazwane |
| Wartość domyślna |brak |
| Akceptujesz dane wejściowe potoku? |fałsz |
| Akceptować symbole wieloznaczne? |fałsz |

### <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
Jeśli wartość jest równa true, Wydrukuj komunikaty ze skryptu do strumienia wyjściowego.

| Aliasy | brak |
| --- | --- |
| Wymagane? |fałsz |
| Położenie |nazwane |
| Wartość domyślna |fałsz |
| Akceptujesz dane wejściowe potoku? |fałsz |
| Akceptować symbole wieloznaczne? |fałsz |

## <a name="remarks"></a>Uwagi
Aby uzyskać pełne wyjaśnienie, jak używać skryptu do tworzenia środowisk deweloperskich i testowych, zobacz [Używanie skryptów programu Windows PowerShell do publikowania w środowiskach deweloperskich i testowych](vs-azure-tools-publishing-using-powershell-scripts.md).

Plik konfiguracji JSON określa szczegóły dotyczące tego, co ma zostać wdrożone. Zawiera informacje, które zostały określone podczas tworzenia projektu, takie jak nazwa, grupa koligacji, obraz VHD i rozmiar maszyny wirtualnej. Obejmuje również punkty końcowe maszyny wirtualnej, bazy danych do aprowizacji, jeśli istnieją i parametry wdrażania w sieci Web. Poniższy kod przedstawia przykładowy plik konfiguracji JSON:

```
{
    "environmentSettings": {
        "cloudService": {
            "name": "myvmname",
            "affinityGroup": "",
            "location": "West US",
            "virtualNetwork": "",
            "subnet": "",
            "availabilitySet": "",
            "virtualMachine": {
                "name": "myvmname",
                "vhdImage": "a699494373c04fc0bc8f2bb1389d6106__Windows-Server-2012-R2-201404.01-en.us-127GB.vhd",
                "size": "Small",
                "user": "vmuser1",
                "password": "",
                "enableWebDeployExtension": true,
                "endpoints": [
                    {
                        "name": "Http",
                        "protocol": "TCP",
                        "publicPort": "80",
                        "privatePort": "80"
                    },
                    {
                        "name": "Https",
                        "protocol": "TCP",
                        "publicPort": "443",
                        "privatePort": "443"
                    },
                    {
                        "name": "WebDeploy",
                        "protocol": "TCP",
                        "publicPort": "8172",
                        "privatePort": "8172"
                    },
                    {
                        "name": "Remote Desktop",
                        "protocol": "TCP",
                        "publicPort": "3389",
                        "privatePort": "3389"
                    },
                    {
                        "name": "Powershell",
                        "protocol": "TCP",
                        "publicPort": "5986",
                        "privatePort": "5986"
                    }
                ]
            }
        },
        "databases": [
            {
                "connectionStringName": "",
                "databaseName": "",
                "serverName": "",
                "user": "",
                "password": ""
            }
        ],
        "webDeployParameters": {
            "iisWebApplicationName": "Default Web Site"
        }
    }
}
```

Plik konfiguracji JSON można edytować, aby zmienić zainicjowaną zawartość. Wymagana jest maszyna wirtualna i usługa w chmurze, ale sekcja bazy danych jest opcjonalna.