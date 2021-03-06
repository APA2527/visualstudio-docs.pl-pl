---
title: '&lt;Signature — &gt; element (wdrożenie ClickOnce) | Microsoft Docs'
description: Element Signature zawiera informacje niezbędne do podpisania cyfrowo tego manifestu wdrożenia. Podpisywanie manifestu wdrożenia jest opcjonalne, ale zalecane.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
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
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 5d95398285d9106719f3c2444d54202b81cfee4a
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99877502"
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;Signature — &gt; element (wdrażanie ClickOnce)
Zawiera informacje niezbędne do podpisania cyfrowo tego manifestu wdrożenia.

## <a name="syntax"></a>Składnia

```xml

<Signature> 
   XML signature information 
</Signature>
```

## <a name="remarks"></a>Uwagi
 Podpisywanie manifestu wdrożenia przy użyciu podpisu koperty jest opcjonalne, ale zalecane. Aby uzyskać więcej informacji na temat podpisywania plików XML, zapoznaj się z zaleceniami organizacja World Wide Web Consortium, "składnią i przetwarzaniem sygnatury XML" opisanymi w temacie [http://www.w3.org/TR/xmldsig-core/](https://www.w3.org/TR/xmldsig-core/) .

 Jeśli chcesz podpisać manifest, należy podać skróty dla wszystkich plików. Nie można podpisać manifestu z plikami, które nie są skrótami, ponieważ użytkownicy nie mogą zweryfikować zawartości plików niebędących skrótami.

## <a name="example"></a>Przykład
 Poniższy przykład kodu ilustruje `Signature` element w manifeście wdrożenia używanym we [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] wdrożeniu.

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
- [Manifest wdrożenia ClickOnce](../deployment/clickonce-deployment-manifest.md)
