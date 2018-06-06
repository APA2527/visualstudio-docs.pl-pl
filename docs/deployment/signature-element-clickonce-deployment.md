---
title: '&lt;Podpis&gt; elementu (wdrażania ClickOnce) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c02a7fb2ab17d5a8f8a8e141814be432a119bf82
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/06/2018
ms.locfileid: "34814963"
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;Podpis&gt; elementu (wdrażania ClickOnce)
Zawiera informacje potrzebne do cyfrowego podpisywania manifestu tego wdrożenia.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
  
      <Signature>   
   XML signature information   
</Signature>  
```  
  
## <a name="remarks"></a>Uwagi  
 Podpisywanie manifestu wdrożenia przy użyciu podpisu koperty jest opcjonalne, ale zalecane. Aby uzyskać więcej informacji na temat podpisywania plików XML, zobacz sieci World Wide Web konsorcjum zalecenia, "Podpis XML składni i przetwarzanie" w sposób opisany w [ http://www.w3.org/TR/xmldsig-core/ ](http://www.w3.org/TR/xmldsig-core/).  
  
 Jeśli chcesz zarejestrować w manifeście, należy podać wartości skrótu dla wszystkich plików. Nie można podpisać manifest z plikami, które nie jest przemieszane, ponieważ użytkownicy nie może zweryfikować zawartości bez haszowania plików.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu pokazuje `Signature` elementu w manifeście wdrażania, używane w [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] wdrożenia.  
  
```xml  
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
  <SignedInfo>  
    <CanonicalizationMethod Algorithm=  
           "http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />  
    <SignatureMethod Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#rsa-sha1" />  
    <Reference URI="">  
      <Transforms>  
        <Transform Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#enveloped-signature" />  
      </Transforms>  
      <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <DigestValue>d2z5AE...</DigestValue>  
    </Reference>  
  </SignedInfo>  
  <SignatureValue>  
4PHj6SaopoLp...  
  </SignatureValue>  
  <KeyInfo>  
    <X509Data>  
      <X509Certificate>  
MIIHnTCCBoWgAwIBAgIKJY9+nwAHAAB...  
      </X509Certificate>  
    </X509Data>  
  </KeyInfo>  
</Signature>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Manifest wdrożenia ClickOnce](../deployment/clickonce-deployment-manifest.md)