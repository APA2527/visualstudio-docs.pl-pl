---
title: '&lt;zestaw&gt; — Element (wdrażanie ClickOnce) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce deployment manifest]
ms.assetid: b8e3362a-f821-4696-b98d-571d4bbfe431
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 5fa45d64956fe1347477abb533e45565f27996f7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259951"
---
# <a name="ltassemblygt-element-clickonce-deployment"></a>&lt;zestaw&gt; — Element (wdrażanie ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Element najwyższego poziomu do manifestu wdrażania.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
      <assembly    
   manifestVersion  
/>  
```  
  
## <a name="elements-and-attributes"></a>Atrybuty i elementy  
 `assembly` Element jest elementem głównym i jest wymagana. Pierwszy element zawarte musi być `assemblyIdentity` elementu. Elementy manifestu musi znajdować się w następujących przestrzeni nazw: `urn:schemas-microsoft-com:asm.v1`, `urn:schemas-microsoft-com:asm.v2`, i `http://www.w3.org/2000/09/xmldsig#`. Elementy podrzędne zestawu również musi być w tych obszarach nazw poprzez dziedziczenie lub oznaczając.  
  
 `assembly` Element ma atrybut.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`manifestVersion`|Wymagane. Ten atrybut musi być równa `1.0`.|  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie kodu pokazano `assembly` elementu w manifeście wdrożenia dla aplikacji wdrożonych za pomocą [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Ten przykład kodu jest częścią większego przykładu przewidzianego dla [Manifest wdrażania ClickOnce](../deployment/clickonce-deployment-manifest.md) tematu.  
  
```  
<asmv1:assembly   
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"  
  manifestVersion="1.0"  
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Manifest wdrażania ClickOnce](../deployment/clickonce-deployment-manifest.md)   
 [\<zestaw > Element](../deployment/assembly-element-clickonce-application.md)



