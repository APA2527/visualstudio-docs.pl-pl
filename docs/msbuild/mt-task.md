---
title: MT — zadanie | Microsoft Docs
description: Informacje o parametrach i opcjach wiersza polecenia programu MSBuild MT, które zawijają narzędzie manifestu firmy Microsoft mt.exe.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VC.Project.VCManifestTool.ResourceOutputFileName
- VC.Project.VCManifestTool.SuppressDependencyElement
- VC.Project.VCManifestTool.ManifestFromManagedAssembly
- VC.Project.VCManifestTool.GenerateCategoryTags
- VC.Project.VCManifestTool.EnableDPIAwareness
- vc.task.mt
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBUILD (C++), MT task
- MT task (MSBuild (C++))
ms.assetid: bb94913c-1042-4968-9f08-b394518e899f
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: a023c58e528b2cda74fa42fcce46fd9c39059459
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99905448"
---
# <a name="mt-task"></a>MT — Zadanie

Zawija narzędzie manifestu firmy Microsoft, *mt.exe*. Aby uzyskać więcej informacji, zobacz [Mt.exe](/windows/desktop/SbsCs/mt-exe).

## <a name="parameters"></a>Parametry

 W poniższej tabeli opisano parametry **MT** zadania. Większość parametrów zadań i kilku zestawów parametrów odpowiada opcji wiersza polecenia.

> [!NOTE]
> W dokumentacji *mt.exe* jest stosowany łącznik ( **-** ) jako prefiks opcji wiersza polecenia, ale w tym temacie jest stosowany ukośnik ( **/** ). Dowolny prefiks jest akceptowalny.

|Parametr|Opis|
|---------------|-----------------|
|**AdditionalManifestFiles**|Opcjonalny parametr **String []** .<br /><br /> Określa nazwę jednego lub więcej plików manifestu.<br /><br /> Aby uzyskać więcej informacji, zobacz **/manifest** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**AdditionalOptions**|Opcjonalny parametr **ciągu** .<br /><br /> Lista opcji wiersza polecenia. Na przykład/ \<option1>  / \<option2>  / \<option#> . Użyj tego parametru, aby określić opcje wiersza polecenia, które nie są reprezentowane przez żaden inny parametr **MT** .<br /><br /> Aby uzyskać więcej informacji, zobacz [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**AssemblyIdentity**|Opcjonalny parametr **ciągu** .<br /><br /> Określa wartości atrybutów elementu **assemblyIdentity** manifestu. Określ listę rozdzielaną przecinkami, gdzie pierwszy składnik jest wartością `name` atrybutu, po którym następuje co najmniej jedna para nazwa/wartość mająca postać, *\<attribute name> =<ATTRIBUTE_VALUE>*.<br /><br /> Aby uzyskać więcej informacji, zobacz **/Identity** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**ComponentFileName**|Opcjonalny parametr **ciągu** .<br /><br /> Określa nazwę biblioteki dołączanej dynamicznie, która ma zostać utworzona na podstawie plików *. RGS* lub *. tlb* . Ten parametr jest wymagany, jeśli określono parametry zadania **RegistrarScriptFile** lub **TypeLibraryFile** Mt.<br /><br /> Aby uzyskać więcej informacji, zobacz **/dll** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**DependencyInformationFile**|Opcjonalny parametr **ciągu** .<br /><br /> Określa plik informacji o zależnościach używany przez program Visual Studio do śledzenia informacji o zależnościach kompilacji dla narzędzia manifestu.|
|**EmbedManifest**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , osadza plik manifestu w zestawie. Jeśli `false` , tworzy jako autonomiczny plik manifestu.|
|**EnableDPIAwareness**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , dodaje do informacji manifestu, który oznacza aplikację jako obsługującą dpi. Pisanie aplikacji z obsługą rozdzielczości DPI sprawia, że interfejs użytkownika wygląda spójnie w wielu różnych ustawieniach wyświetlania o wysokiej rozdzielczości DPI.<br /><br /> Aby uzyskać więcej informacji, zobacz [wysokiej rozdzielczości DPI](/windows/desktop/win7devguide/high-dpi).|
|**GenerateCatalogFiles**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , generuje pliki definicji katalogu (*. cdf*).<br /><br /> Aby uzyskać więcej informacji, zobacz **/makecdfs** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**GenerateCategoryTags**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , powoduje, że Tagi kategorii mają być generowane. Jeśli ten parametr ma wartość `true` , należy również określić parametr zadania **ManifestFromManagedAssemblyMT** .<br /><br /> Aby uzyskać więcej informacji, zobacz **/Category** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**InputResourceManifests**|Opcjonalny parametr **ciągu** .<br /><br /> Wprowadź manifest z zasobu typu RT_MANIFEST o określonym identyfikatorze. Określ zasób formularza \<file> [; [ #] \<resource_id> ], gdzie opcjonalny \<resource_id> parametr ma wartość nieujemną, 16-bitową.<br /><br /> Jeśli nie `resource_id` jest określony, zostanie użyta wartość domyślna CREATEPROCESS_MANIFEST_RESOURCE (1).<br /><br /> Aby uzyskać więcej informacji, zobacz **/inputresource** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**ManifestFromManagedAssembly**|Opcjonalny parametr **ciągu** .<br /><br /> Generuje manifest z określonego zarządzanego zestawu.<br /><br /> Aby uzyskać więcej informacji, zobacz **/managedassemblyname** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**ManifestToIgnore**|Opcjonalny parametr **ciągu** .<br /><br /> (Nieużywane).|
|**OutputManifestFile**|Opcjonalny parametr **ciągu** .<br /><br /> Określa nazwę manifestu danych wyjściowych. Jeśli ten parametr zostanie pominięty i tylko jeden manifest jest obsługiwany na, ten manifest jest modyfikowany.<br /><br /> Aby uzyskać więcej informacji, zobacz opcję **/out** w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**OutputResourceManifests**|Opcjonalny parametr **ciągu** .<br /><br /> Dane wyjściowe manifestu do zasobu typu RT_MANIFEST o określonym identyfikatorze. Zasób ma postać \<file> [; [ #] \<resource_id> ], gdzie opcjonalny \<resource_id> parametr ma wartość nieujemną, 16-bitową.<br /><br /> Jeśli nie `resource_id` jest określony, zostanie użyta wartość domyślna CREATEPROCESS_MANIFEST_RESOURCE (1).<br /><br /> Aby uzyskać więcej informacji, zobacz **/outputresource** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**RegistrarScriptFile**|Opcjonalny parametr **ciągu** .<br /><br /> Określa nazwę pliku skryptu rejestratora (*. RGS*), który ma być używany do obsługi manifestu COM bez rejestracji.<br /><br /> Aby uzyskać więcej informacji, zobacz **/RGS** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**ReplacementsFile**|Opcjonalny parametr **ciągu** .<br /><br /> Określa plik, który zawiera wartości dla wymiennych ciągów w pliku skryptu rejestratora (*. RGS*).<br /><br /> Aby uzyskać więcej informacji, zobacz **/replacements** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**ResourceOutputFileName**|Opcjonalny parametr **ciągu** .<br /><br /> Określa plik zasobów wyjściowych służący do osadzenia manifestu w danych wyjściowych projektu.|
|**Źródła**|Opcjonalny `ITaskItem[]` parametr.<br /><br /> Określa listę plików źródłowych manifestu rozdzielonych spacjami.<br /><br /> Aby uzyskać więcej informacji, zobacz **/manifest** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**SuppressDependencyElement**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , generuje manifest bez elementów zależności. Jeśli ten parametr ma wartość `true` , należy również określić parametr zadania **ManifestFromManagedAssemblyMT** .<br /><br /> Aby uzyskać więcej informacji, zobacz **/nodependency** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**SuppressStartupBanner**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , program zapobiega wyświetlaniu komunikatu o prawach autorskich i numerze wersji, gdy zadanie zostanie uruchomione.<br /><br /> Aby uzyskać więcej informacji, zobacz **/nologo** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**Katalog trackerlogdirectory**|Opcjonalny `String` parametr.<br /><br /> Określa katalog pośredni, w którym są przechowywane dzienniki śledzenia dla tego zadania.|
|**TypeLibraryFile**|Opcjonalny parametr **ciągu** .<br /><br /> Określa nazwę pliku biblioteki typów (*. tlb*). W przypadku określenia tego parametru należy także określić parametr zadania **ComponentFileNameMT** .<br /><br /> Aby uzyskać więcej informacji, zobacz **/TLB** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|
|**UpdateFileHashes**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , oblicza wartość skrótu plików w ścieżce określonej przez parametr zadania **UpdateFileHashesSearchPathMT** , a następnie aktualizuje wartość atrybutu **hash** elementu **pliku** manifestu przy użyciu wartości obliczanej.<br /><br /> Aby uzyskać więcej informacji, zobacz **/hashupdate** opcji w [Mt.exe](/windows/desktop/SbsCs/mt-exe). Zobacz również parametr **UpdateFileHashesSearchPath** w tej tabeli.|
|**UpdateFileHashesSearchPath**|Opcjonalny `String` parametr.<br /><br /> Określa ścieżkę wyszukiwania do użycia podczas aktualizowania skrótów plików. Użyj tego parametru z parametrem zadania **UpdateFileHashesMT** .<br /><br /> Aby uzyskać więcej informacji, zobacz **UpdateFileHashes** parametr w tej tabeli.|
|**VerboseOutput**|Opcjonalny `Boolean` parametr.<br /><br /> Jeśli `true` , wyświetla pełne informacje o debugowaniu.<br /><br /> Aby uzyskać więcej informacji, zobacz opcję **/verbose** w [Mt.exe](/windows/desktop/SbsCs/mt-exe).|

## <a name="see-also"></a>Zobacz też

- [Dokumentacja zadań](../msbuild/msbuild-task-reference.md)
