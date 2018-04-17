---
title: '&lt;PackageFiles&gt; elementu (programu inicjującego) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <PackageFiles> element [bootstrapper]
ms.assetid: 3ea252d7-18a3-47d8-af83-47feebcfe82b
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: f58a9d2ca9bf77a2119e0b2a2716c96676889568
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="ltpackagefilesgt-element-bootstrapper"></a>&lt;PackageFiles&gt; elementu (programu inicjującego)
`PackageFiles` Element zawiera `PackageFile` elementów, które określają pakiety instalacyjne wykonywane w `Command` elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
<PackageFiles  
    CopyAllPackageFiles  
>  
    <PackageFile   
        Name  
        HomeSite  
        CopyOnBuild  
        PublicKey  
        Hash  
    />  
</PackageFiles>  
```  
  
## <a name="elements-and-attributes"></a>Elementy i atrybuty  
 `PackageFiles` Element ma następującego atrybutu.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`CopyAllPackageFiles`|Opcjonalny. Jeśli ustawiono `false`, Instalator pobierze tylko pliki, do których odwołuje się z `Command` elementu. Jeśli ustawiono `true`, wszystkie pliki zostaną pobrane.<br /><br /> Jeśli ustawioną `IfNotHomesite`, Instalator będzie działają tak samo, jakby `False` Jeśli `ComponentsLocation` ma ustawioną wartość `HomeSite`, a w przeciwnym razie będą zachowywać się takie same tak, jakby `True`. To ustawienie może być przydatne umożliwia pakiety, które same bootstrappers do wykonania ich zachowania w przypadku scenariusza HomeSite.<br /><br /> Wartość domyślna to `true`.|  
  
## <a name="packagefile"></a>PackageFile  
 `PackageFile` Element jest elementem podrzędnym `PackageFiles` elementu. A `PackageFiles` element musi mieć co najmniej jeden `PackageFile` elementu.  
  
 `PackageFile` ma następujące atrybuty.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`Name`|Wymagany. Nazwa pliku pakietu. Jest to nazwa, która `Command` element będzie stanowiła odwołanie podczas definiuje warunki, w których instaluje pakiet. Ta wartość jest również używany jako klucz w `Strings` tabelę, aby pobrać zlokalizowana nazwa, która narzędzi takich jak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] będzie używać do opisywania pakietu.|  
|`HomeSite`|Opcjonalny. Lokalizacja pakietu na serwerze zdalnym, jeśli nie jest dołączony do Instalatora.|  
|`CopyOnBuild`|Opcjonalny. Określa, czy program inicjujący skopiuj plik pakietu na dysku w czasie kompilacji. Wartość domyślna to true.|  
|`PublicKey`|Zaszyfrowany klucz publiczny podpisu certyfikatu pakietu. Jeśli wymagane `HomeSite` jest używany; w przeciwnym razie opcjonalne.|  
|`Hash`|Opcjonalny. Skrót SHA1 pliku pakietu. Służy to sprawdzenie integralności plik w czasie instalacji. Jeśli nie można obliczyć skrótu identyczne z pliku pakietu, nie można zainstalować pakietu.|  
  
## <a name="example"></a>Przykład  
 Poniższy przykładowy kod definiuje pakietów dla [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pakietu redystrybucyjnego i jego zależności, takich jak Instalator Windows.  
  
```  
<PackageFiles>  
    <PackageFile Name="instmsia.exe" HomeSite="InstMsiAExe" PublicKey="3082010A0282010100AA99BD39A81827F42B3D0B4C3F7C772EA7CBB5D18C0DC23A74D793B5E0A04B3F595ECE454F9A7929F149CC1A47EE55C2083E1220F855F2EE5FD3E0CA96BC30DEFE58C82732D08554E8F09110BBF32BBE19E5039B0B861DF3B0398CB8FD0B1D3C7326AC572BCA29A215908215E277A34052038B9DC270BA1FE934F6F335924E5583F8DA30B620DE5706B55A4206DE59CBF2DFA6BD154771192523D2CB6F9B1979DF6A5BF176057929FCC356CA8F440885558ACBC80F464B55CB8C96774A87E8A94106C7FF0DE968576372C36957B443CF323A30DC1BE9D543262A79FE95DB226724C92FD034E3E6FB514986B83CD0255FD6EC9E036187A96840C7F8E203E6CF050203010001"/>  
    <PackageFile Name="WindowsInstaller-KB884016-v2-x86.exe" HomeSite="Msi30Exe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetfx.exe" HomeSite="DotNetFXExe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetchk.exe"/>  
</PackageFiles>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [\<Produktu > — Element](../deployment/product-element-bootstrapper.md)   
 [\<Pakiet > — Element](../deployment/package-element-bootstrapper.md)   
 [Produkt i pakiet — dokumentacja schematu](../deployment/product-and-package-schema-reference.md)