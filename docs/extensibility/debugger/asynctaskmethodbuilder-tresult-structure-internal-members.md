---
title: '&lt;Struktura TResult AsyncTaskMethodBuilder &gt; — wewnętrzne elementy członkowskie | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- AsyncTaskMethodBuilder<TResult> structure [.NET Framework debug engines]
- debug engines, AsyncTaskMethodBuilder<TResult> structure [.NET Framework]
ms.assetid: 17ebc340-8170-4aff-bf54-dc4548c83632
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 41cb409495b28b7dc2bc796859da413a32b90d85
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2021
ms.locfileid: "99921634"
---
# <a name="asynctaskmethodbuilderlttresultgt-structure---internal-members"></a>&lt;Struktura TResult AsyncTaskMethodBuilder &gt; — elementy wewnętrzne
W tym temacie opisano wewnętrzne elementy członkowskie <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> klasy. Aby uzyskać ogólne informacje na temat tej klasy, zobacz temat informacje o <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> odwołaniach.

 **Przestrzeń nazw:**<xref:System.Runtime.CompilerServices?displayProperty=fullName>

 **Zestaw:** mscorlib (w mscorlib.dll)

 Ponieważ nie można uzyskać dostępu do tych wewnętrznych elementów członkowskich z .NET Framework, następująca składnia jest udostępniana w typowym języku pośrednim (CIL).

## <a name="syntax"></a>Składnia

```csharp
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<TResult>
       extends System.ValueType
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder
```

## <a name="internal-members"></a>Wewnętrzne elementy członkowskie

|Nazwa|Opis|
|----------|-----------------|
|[Właściwość ObjectIdForDebugger](../../extensibility/debugger/asynctaskmethodbuilder-tresult-objectidfordebugger-property.md)|Pobiera obiekt, który może być używany do jednoznacznego identyfikowania tego konstruktora w debugerze.|
|[pole m_task](../../extensibility/debugger/asynctaskmethodbuilder-tresult-m-task-field.md)|Reprezentuje wbudowane zadanie opóźnieniem.|

## <a name="see-also"></a>Zobacz też
- <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>
- [Wewnętrzne rozszerzenia równoległe dla .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
