---
title: '&lt;RelatedProducts&gt; — Element (program inicjujący) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- MSBuild.GenerateBootstrapper.MissingDependency
- MSBuild.GenerateBootstrapper.DuplicateItems
- MSBuild.GenerateBootstrapper.IncludedProductIncluded
- MSBuild.GenerateBootstrapper.DependencyNotFound
- MSBuild.GenerateBootstrapper.PackageFileNotFound
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <RelatedProducts> element [bootstrapper]
ms.assetid: bf152712-4c1e-48bd-9b7f-311cf0fdb832
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c541a9775025183a3b3ffbf21ef5b72c3f00cc87
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077811"
---
# <a name="ltrelatedproductsgt-element-bootstrapper"></a>&lt;RelatedProducts&gt; — element (program inicjujący)
`RelatedProducts` Element definiuje innych produktów, które zależą od lub znajdują się w bieżącym produkcie.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<RelatedProducts>  
    <DependsOnProduct  
        Code  
    />  
    <EitherProducts>  
        <DependsOnProduct  
            Code  
        />  
    </EitherProducts>  
    <IncludesProduct  
        Code  
    />  
</RelatedProducts>  
```  
  
## <a name="elements-and-attributes"></a>Atrybuty i elementy  
 `RelatedProducts` Element jest elementem podrzędnym `Product` elementu. Go nie ma żadnych atrybutów.  
  
## <a name="dependsonproduct"></a>DependsOnProduct  
 `DependsOnProduct` Element oznacza, że bieżącego produktu zależy od wskazanego produktu i że wskazanego produktu powinien zostać zainstalowany przed bieżącym. Jest elementem podrzędnym `RelatedProducts` elementu. A `RelatedProducts` element może mieć co najmniej jeden `DependsOnProduct` elementów.  
  
 `DependsOnProduct` ma następujący atrybut.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`Code`|Nazwa kodu produktu uwzględniona, określony przez `ProductCode` atrybutu `Product` elementu. Aby uzyskać więcej informacji, zobacz [ \<produktu > Element](../deployment/product-element-bootstrapper.md).|  
  
## <a name="eitherproducts"></a>EitherProducts  
 `EitherProducts` Element definiuje zero lub więcej `DependsOnProduct` elementów, a nie ma żadnych atrybutów. Co najmniej jeden `DependsOnProduct` w tym zestawie musi zostać zainstalowany przed bieżącego produktu. A `RelatedProducts` element może mieć zero lub więcej `EitherProducts` elementów.  
  
## <a name="includesproduct"></a>IncludesProduct  
 `IncludesProduct` Element oznacza znajduje się w bieżącej instalacji produktu i nie wymagają oddzielnej instalacji. Jest elementem podrzędnym `RelatedProducts` elementu. A `RelatedProducts` element może mieć co najmniej jeden `IncludesProduct` elementów.  
  
 `IncludesProduct` ma następujący atrybut.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`Code`|Nazwa kodu produktu uwzględniona, określony przez `ProductCode` atrybutu `Product` elementu. Aby uzyskać więcej informacji, zobacz [ \<produktu > Element](../deployment/product-element-bootstrapper.md).|  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu Określa, że Microsoft Installer został zainstalowany z [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]i w związku z tym nie wymagają oddzielnej instalacji.  
  
```xml  
<RelatedProducts>  
    <IncludesProduct Code="Microsoft.Windows.Installer.2.0" />  
</RelatedProducts>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [\<Produktu > element](../deployment/product-element-bootstrapper.md)