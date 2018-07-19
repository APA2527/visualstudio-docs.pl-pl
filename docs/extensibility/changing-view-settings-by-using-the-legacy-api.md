---
title: Zmienianie ustawień widoku za pomocą starszej wersji interfejsu API | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - changing view settings
ms.assetid: 12c9b300-0894-4124-96a1-764326176d77
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f92c4146cc40aff6cf4c73ab3652f68f33a27b51
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077971"
---
# <a name="change-view-settings-by-using-the-legacy-api"></a>Zmienianie ustawień widoku przy użyciu starszej wersji interfejsu API
Ustawienia podstawowe funkcje edytora, takie jak zawijanie wyrazów, margines zaznaczania i wirtualną przestrzenią, można zmienić przez użytkownika przez **opcje** okno dialogowe. Jednak istnieje również możliwość zmiany tych ustawień programowo.  
  
## <a name="change-settings-by-using-the-legacy-api"></a>Zmień ustawienia za pomocą starszej wersji interfejsu API  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> Interfejsu ujawnia zestaw właściwości edytora tekstu. Wyświetl tekst zawiera kategorię właściwości (GUID_EditPropCategory_View_MasterSettings), która reprezentuje grupę programowo zmienione ustawienia widoku tekstu. Gdy ustawienia wyświetlania zostały zmienione w ten sposób, nie można zmienić w **opcje** okno dialogowe, dopóki nie są one resetowane.  
  
 Poniżej przedstawiono typowy proces dotyczące zmieniania ustawień widoku dla wystąpienia podstawowy edytor.  
  
1.  Wywołaj `QueryInterface` na (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>) dla <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> interfejsu.  
  
2.  Wywołaj <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> metody, określając wartość GUID_EditPropCategory_View_MasterSettings dla `rguidCategory` parametru.  
  
     W ten sposób zwraca wskaźnik do <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> interfejs, który zawiera zbiór właściwości wymuszone dla widoku. Wszystkie ustawienia w tej grupie są stale wymuszone. Jeśli to ustawienie nie jest w tej grupie, a następnie będzie przestrzegany opcji określonych w **opcje** okno dialogowe lub przez użytkownika polecenia.  
  
3.  Wywołaj <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> metody, określając wartość odpowiednie ustawienia w `idprop` parametru.  
  
     Na przykład aby wymusić zawijanie wyrazów, należy wywołać <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> i określ wartość VSEDITPROPID_ViewLangOpt_WordWrap, `vt` dla `idprop` parametru. W tym wywołaniu `vt` jest wariant typu VT_BOOL i `vt.boolVal` jest VARIANT_TRUE.  
  
## <a name="reset-changed-view-settings"></a>Resetowanie zmienić ustawienia widoku  
 Aby zresetować wszystkie zmienione ustawienie dla wystąpienia podstawowy edytor widoku, należy wywołać <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> metody i określ wartość odpowiednie ustawienie w `idprop` parametru.  
  
 Na przykład, aby umożliwić zawijanie wyrazów, które można dowolnie przesuwać, należy usunąć go z kategorii właściwości przez wywołanie metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> i określenie wartości VSEDITPROPID_ViewLangOpt_WordWrap dla `idprop` parametru.  
  
 Aby usunąć wszystkie zmienione ustawienia edytora podstawowych jednocześnie, określ wartość VSEDITPROPID_ViewComposite_AllCodeWindowDefaults, vt dla `idprop` parametru. W tym wywołaniu vt jest wariant typu VT_BOOL, i vt.boolVal jest VARIANT_TRUE.  
  
## <a name="see-also"></a>Zobacz także  
 [W edytorze podstawowych](../extensibility/inside-the-core-editor.md)   
 [Wyświetl theText dostępu przy użyciu starszej wersji interfejsu API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)   
 [Opcje, okno dialogowe](../ide/reference/options-dialog-box-visual-studio.md)