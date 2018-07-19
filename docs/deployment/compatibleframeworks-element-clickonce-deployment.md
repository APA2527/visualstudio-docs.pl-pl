---
title: '&lt;compatibleFrameworks&gt; — Element (wdrażanie ClickOnce) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44329fc4c2ec5e9f2f8352d69ea487f23cbe3c5a
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077688"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt; — element (wdrażanie ClickOnce)
Identyfikuje wersje programu .NET Framework, gdzie tę aplikację można instalować i uruchamiać.  
  
> [!NOTE]
>  [*MageUI.exe* ](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client) nie obsługuje `compatibleFrameworks` elementu podczas zapisywania manifestu aplikacji, która została już podpisana za pomocą certyfikatu za pomocą [ *MageUI.exe*](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Zamiast tego należy użyć [ *Mage.exe*](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## <a name="elements-and-attributes"></a>Atrybuty i elementy  
 `compatibleFrameworks` Element jest wymagany, dla których obiektem docelowym manifesty wdrożenia [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] runtime udostępnianym przez [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] lub nowszej. `compatibleFrameworks` Elementu zawiera jeden lub więcej `framework` elementy, które określają wersje programu .NET Framework, na których można uruchomić tę aplikację. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Środowisko uruchomieniowe będzie uruchomić aplikację na pierwszy dostępny `framework` na tej liście.  
  
 Poniższa tabela zawiera listę atrybutów, `compatibleFrameworks` obsługuje element.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`S``upportUrl`|Opcjonalna. Określa adres URL, gdzie można pobrać preferowanych zgodnej wersji programu .NET Framework.|  
  
## <a name="framework"></a>szablon  
 Wymagane. W poniższej tabeli przedstawiono atrybuty, `framework` obsługuje element.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`targetVersion`|Wymagane. Określa numer wersji obiektu docelowego .NET Framework.|  
|`profile`|Wymagane. Określa profil docelową aplikację .NET Framework.|  
|`supportedRuntime`|Wymagane. Określa numer wersji środowiska uruchomieniowego, skojarzone z docelową aplikację .NET Framework.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="example"></a>Przykład  
 Poniższy kod przedstawia przykład `compatibleFrameworks` element [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest wdrożenia. Tego wdrożenia można uruchomić na [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]. Można również uruchomić na [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] jest nadzbiorem [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].  
  
```xml  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Manifest wdrażania ClickOnce](../deployment/clickonce-deployment-manifest.md)