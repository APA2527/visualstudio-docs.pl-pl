---
title: "Wywołanie P CA5122 deklaracje nie powinny być bezpieczne krytyczne | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4d012b1fc37090f382d73dab73f1c302207edd30
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="ca5122-pinvoke-declarations-should-not-be-safe-critical"></a>CA5122 Deklaracje P/Invoke nie powinny być bezpieczne-krytyczne
|||  
|-|-|  
|TypeName|PInvokesShouldNotBeSafeCriticalFxCopRule|  
|CheckId|CA5122|  
|Kategoria|Microsoft.Security|  
|Zmiana kluczowa|Kluczowa|  
  
## <a name="cause"></a>Przyczyna  
 Deklaracja P/Invoke zostały oznaczone <xref:System.Security.SecuritySafeCriticalAttribute>:  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers]  
  
// ...  
public class C  
{  
    [SecuritySafeCritical]  
    [DllImport("kernel32.dll")]  
    public static extern bool Beep(int frequency, int duration); // CA5122 - safe critical p/invoke  
   }  
  
```  
  
 W tym przykładzie `C.Beep(...)` została oznaczona jako metoda krytyczne bezpieczne zabezpieczeń.  
  
## <a name="rule-description"></a>Opis reguły  
 Metody są oznaczone jako SecuritySafeCritical, gdy wykonują operacje zależne od zabezpieczeń, ale mogą być również bezpiecznie używane przez kod przezroczystości. Jedną z podstawowych reguł zabezpieczeń modelu przezroczystości jest to, że przezroczysty kod nigdy nie może bezpośrednio wywołać kodu natywnego za pośrednictwem metody P/Invoke. Dlatego oznakowanie metody P/Invoke jako bezpiecznej-krytycznej pod względem zabezpieczeń nie umożliwi jej wywołania kodu przezroczystości i jest mylące dla analizy zabezpieczeń.  
  
## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia  
 Aby metoda P/Invoke stała się dostępna dla przejrzystego kodu, należy ujawnić dla niej bezpieczną-krytyczną pod względem zabezpieczeń metodę dla otoki:  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers  
  
class C  
{  
   [SecurityCritical]  
   [DllImport("kernel32.dll", EntryPoint="Beep")]  
   private static extern bool BeepPinvoke(int frequency, int duration); // Security Critical P/Invoke  
  
   [SecuritySafeCritical]  
   public static bool Beep(int frequency, int duration)  
   {  
      return BeepPInvoke(frequency, duration);  
   }  
}  
  
```  
  
## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia  
 Nie pomijaj ostrzeżeń dla tej reguły.