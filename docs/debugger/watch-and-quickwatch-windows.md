---
title: Ustawianie wyrażenia kontrolnego na zmiennych w programie Visual Studio | Dokumentacja firmy Microsoft
ms.custom: H1Hack27Feb2017
ms.date: 04/04/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.watch
helpviewer_keywords:
- debugging [Visual Studio], Watch window
- expressions [debugger], evaluating
- variables [debugger], evaluating
- expression evaluation
- registers, evaluating
- debugging [Visual Studio], expression evaluation
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aaba3f16ccf08fa56e6f529192ae9ad9cab6d496
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42635440"
---
# <a name="set-a-watch-on-variables-using-the-watch-and-quickwatch-windows-in-visual-studio"></a>Ustawianie wyrażenia kontrolnego na zmiennych przy użyciu wyrażenie kontrolne i QuickWatch Windows w programie Visual Studio
Podczas debugowania, można użyć **Obejrzyj** i **QuickWatch** systemu windows, aby obejrzeć zmiennych i wyrażeń.  Różnica jest to, że **Obejrzyj** można wyświetlić w oknie kilku zmiennych podczas **QuickWatch** okno wyświetla pojedynczą zmienną w czasie. 

Systemu windows są dostępne tylko podczas sesji debugowania. Aby otworzyć **Obejrzyj** oknie Wybierz **debugowania > Windows > Obejrzyj > Obejrzyj (1, 2, 3, 4)**). Aby otworzyć **QuickWatch** okna, albo kliknij prawym przyciskiem myszy na zmiennej i wybierz **QuickWatch** lub wybierz **Debuguj > QuickWatch**.
  
## <a name="observing-a-single-variable-with-quickwatch"></a>Monitorowanie pojedynczej zmiennej za pomocą QuickWatch  
 Możesz użyć **QuickWatch** okna, aby obserwować w pojedynczej zmiennej. Na przykład, jeśli masz następujący kod:  
  
```csharp
static void Main(string[] args)  
{  
    int a, b;  
    a = 1;  
    b = 2;  
    for (int i = 0; i < 10; i++)  
    {  
        a = a + b;  
    }   
}  
```  
  
 Zmienna w oknie QuickWatch można obserwować w następujący sposób:  
  
1.  Ustaw punkt przerwania na `a = a + b;` wiersza.  
  
2.  Rozpocznij debugowanie. Zatrzymuje wykonywanie w punkcie przerwania.  
  
3.  Otwórz **QuickWatch** okna (kliknij prawym przyciskiem myszy `a`, następnie wybierz **QuickWatch**, lub wybierz `a` i naciśnij klawisz **SHIFT + F9**).

    Powinien zostać wyświetlony zmiennej w **wartości** okna o wartości 1.

    ![QuickWatch Expression](../debugger/media/watchexpression.png "QuickWatchExpression")  

    Jeśli chcesz szacować wyrażenia za pomocą zmiennej, Dodaj wyrażenie, takie jak `a + b` do **wyrażenie** oknie i kliknij przycisk **to ponowne ocenienie**. 
  
4.  Dodaj zmienną **Obejrzyj** w oknie **QuickWatch** , klikając **Dodaj czujkę**. 

    > [!NOTE]
    > **QuickWatch** okno jest oknem modalne okno dialogowe, więc nie można kontynuować debugowanie tak długo, jak jest otwarty.  
  
5.  Zamknij **QuickWatch** okna. Teraz można kontynuować debugowanie podczas obserwowania wartość w **Obejrzyj** okna.  
  
## <a name="observing-variables-with-the-watch-window"></a>Obserwowanie zmiennych z okna czujki  
 Możesz obserwować wiele zmiennych o **Obejrzyj** okna. Na przykład, jeśli masz następujący kod:  
  
```C++  
int main()
{
    int a, b, c;
    a = 1;
    b = 2;
    c = 0;

    for (int i = 0; i < 10; i++)
    {
        a++;
        b *= 2;
        c = a + b;
    }

    return 0;
}
  
```  
  
 Dodaj wartości trzy zmienne w oknie czujki w następujący sposób:  
  
1.  Ustaw punkt przerwania na `c = a + b;` wiersza.  
  
2.  Rozpocznij debugowanie (**F5**). Zatrzymuje wykonywanie w punkcie przerwania.  
  
3.  Otwórz okno czujki (**Debuguj > Windows > Obejrzyj > Czujka 1**, lub **CTRL + ALT + W, 1**).  
  
4.  Dodaj `a` zmiennej w pierwszym wierszu `b` zmiennej do drugiego wiersza i `c` zmienną trzeciego wiersza.

    Zmienne można dodawać, klikając pusty wiersz, a następnie wpisując nazwę zmiennej.
  
5.  Kontynuuj debugowanie (naciśnij klawisz **F11** Aby awansować debuger).  
  
 Powinien zostać wyświetlony wartości zmiennych zmieniają się wraz z iteracyjne przeglądanie `for` pętli.  
  
 Jeśli programujesz w kodzie macierzystym, czasami konieczne może być zakwalifikowanie kontekstu nazwy zmiennej lub wyrażenia zawierającego nazwę zmiennej. Kontekst jest funkcja, plik źródłowy i moduł, w którym znajduje się zmienna. Jeśli ma być zakwalifikowanie kontekstu, można użyć składni operatora kontekstu. Aby uzyskać więcej informacji, zobacz [kontekstu — Operator (C++)](../debugger/context-operator-cpp.md).  
  
## <a name="observing-expressions-with-the-watch-window"></a>Monitorowanie wyrażenia w oknie czujki  
 Teraz Wypróbujmy użycie zamiast tego wyrażenia. Możesz dodać dowolne prawidłowe wyrażenie rozpoznawanym przez debuger.  
  
 Na przykład jeśli masz kod przedstawiony w poprzedniej sekcji, można uzyskać średnią z trzech wartości następująco:  
  
 ![Watch Expression](../debugger/media/watchexpression.png "WatchExpression")  
  
 Ogólnie rzecz biorąc, reguły oceny wyrażenia w **Obejrzyj** okna są takie same jak reguły oceny wyrażenia w swoim języku programowania. Jeśli wyrażenie zawiera błąd składniowy, można oczekiwać, że ten sam błąd kompilatora, które są widoczne w edytorze kodu. Oto przykład:  
  
 ![Obejrzyj błąd wyrażenia](../debugger/media/watchexpressionerror.png "WatchExpressionError")  
  
##  <a name="bkmk_refreshWatch"></a> Odświeżanie wartości czujki, które są nieaktualne  
 W pewnych okolicznościach może być widoczna jest ikona odświeżania (strzałka cykliczne) gdy wyrażenie jest obliczane w **Obejrzyj** okna.  Na przykład, jeśli masz oceny właściwości wyłączony (**Narzędzia > Opcje > debugowanie > Włącz obliczanie właściwości i inne niejawne wywołania funkcji**), i masz następujący kod:  
  
```csharp  
static void Main(string[] args)  
{  
    List<string> list = new List<string>();  
    list.Add("hello");  
    list.Add("goodbye");  
}  
  
```  
  
 Jeśli zostanie ustawiona na wyrażenie kontrolne `Count` właściwości listy, powinien zostać wyświetlony podobną do następującej:  
  
 ![RefreshWatch](../debugger/media/refreshwatch.png "RefreshWatch")  
  
 Na poprzedniej ilustracji przedstawiono błąd lub wartość, która jest nieaktualna. Ogólnie odświeżanie jest możliwe wartości, klikając ikonę, ale w niektórych przypadkach może nie chcesz odświeżać je. Najpierw musisz znać, dlaczego wartość nie został oceniony.  
  
 Po wskazaniu ikonę etykietka narzędzia informacje na temat przyczyny nie zostało obliczone wyrażenie.  Jeśli circling strzałki na liście, wyrażenie nie zostało ocenione pod kątem jednego z następujących powodów:  
  
-   Wystąpił błąd, ponieważ obliczania wyrażenia. Na przykład limit czasu może wystąpić lub zmienną mogły być poza zakres tej asysty.  
  
-   Wyrażenie zawiera wywołanie funkcji, który może wywołać efekt uboczny, w aplikacji (zobacz [efekty uboczne i wyrażenia](#bkmk_sideEffects)).  
  
-   Automatycznej oceny właściwości i wywołania niejawnych funkcji przez debuger jest wyłączona (**Narzędzia > Opcje > debugowanie > Włącz obliczanie właściwości i inne niejawne wywołania funkcji**), a następnie nie może być wyrażenie obliczane automatycznie.  
  
 Aby odświeżyć wartość, kliknij ikonę odświeżania, lub naciśnij klawisz spacji. Debuger próbuje ponownie oceń wyrażenie. Jeśli ikona odświeżania znajdowała się, ponieważ automatycznej oceny właściwości i inne niejawne wywołania funkcji zostało wyłączone, można obliczyć wyrażenia.  
  
 Jeśli widzisz ikonę która zostanie koło z dwóch falistych linii, które przypominają wątków, wyrażenie nie zostało ocenione ze względu na potencjalne zależności między wątkami. Innymi słowy obliczenie kodu wymaga innych wątków w aplikacji w celu tymczasowego uruchomienia. Podczas pracy w trybie przerwania, wszystkie wątki w aplikacji zwykle są zatrzymywane. Zezwolenie tymczasowego uruchomienia innych wątków może mieć nieoczekiwane wpływ na stan programu i powoduje, że debuger Ignoruj zdarzenia, takie jak punkty przerwania i wyjątków zgłaszanych na te wątki.  
  
##  <a name="bkmk_sideEffects"></a> Efekty uboczne i wyrażenia  
 Obliczenie niektórych wyrażeń może zmienić wartość zmiennej lub inaczej wpłynąć na stan programu. Na przykład obliczenie następującego wyrażenia zmienia wartość `var1`:  
  
```csharp
var1 = var2  
```  
  
 Ten kod może spowodować, że [efekt uboczny](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)). Efekty uboczne może utrudnić debugowanie bardziej przez zmianę sposobu działania programu.  
  
 Wyrażenie ma efekty uboczne, jest oceniane tylko raz, po przejściu go. Kolejne oceny są wyłączone. Można ręcznie przezwyciężyć takie działanie, klikając ikonę uaktualnienia, która pojawia się obok wartości.  
  
 Jest jednym ze sposobów, aby uniknąć ze wszystkimi efektami ubocznymi, aby wyłączyć funkcję automatycznej oceny (**Narzędzia > Opcje > debugowanie > Włącz obliczanie właściwości i inne niejawne wywołania funkcji**).  
  
 Podczas oceny właściwości i niejawne wywołania funkcji jest wyłączone, możesz wymusić oceny za pomocą **ac** format modyfikator (tylko język C#). Zobacz [Specyfikatory w języku C# formatu](../debugger/format-specifiers-in-csharp.md).  
  
## <a name="bkmk_objectIds"></a> Za pomocą identyfikatorów obiektów w oknie czujki (C# i Visual Basic)  

 Istnieją terminy, gdy zachodzi potrzeba przyjrzeć się zachowaniu określonego obiektu. Na przykład można śledzić obiekt określony przez zmienną lokalną przeszedł do tej zmiennej poza zakres tej asysty. W języku C# i Visual Basic można utworzyć obiektu identyfikatory dla konkretnych wystąpień typów referencyjnych i używać ich w oknie czujki i warunków punktu przerwania. Identyfikator obiektu jest generowany przez środowisko uruchomieniowe języka wspólnego (CLR) debugowanie usług i powiązane z obiektem.  
  
> [!NOTE]
>  Identyfikatory obiektów Utwórz słabe odwołania i uniemożliwia obiektu jako elementu bezużytecznego zbierane. Są one prawidłowe tylko dla bieżącej sesji debugowania.  
  
 Poniższy kod tworzy jedną metodę `Person` przy użyciu zmiennej lokalnej, ale chcesz dowiedzieć się, jakie `Person`jego nazwa jest w innej metodzie:  
  
```csharp  
class Person  
{  
    public Person(string name)  
    {  
        Name = name;  
    }  
    public string Name { get; set; }  
}  
  
public class Program  
{  
    List<Person> _people = new List<Person>();  
    public static void Main(string[] args)  
    {  
        MakePerson();  
        DoSomething();  
    }  
  
    private static void MakePerson()  
    {  
        var p = new Person("Bob");  
        _people.Add(p);  
    }  
  
    private static void DoSomething()  
    {  
        // more processing  
         Console.WriteLine("done");  
    }  
}  
  
```  
  
 Można dodać odwołanie do tego `Person` obiektu **Obejrzyj** okna w następujący sposób:  
  
1.  Ustaw punkt przerwania w kodzie na pewien czas, po utworzeniu obiektu.  
  
2.  Rozpocznij debugowanie, a po zatrzymaniu w punkcie przerwania wykonywania odnaleźć zmiennej w **lokalne** okna, kliknij go prawym przyciskiem myszy, a następnie wybierz pozycję **wprowadzić identyfikator obiektu**.  
  
3.  Powinien zostać wyświetlony **$** oraz liczbą **lokalne** okna, które reprezentuje identyfikator obiektu.  
  
4.  Dodaj identyfikator obiektu w oknie czujki.  
  
5.  Ustaw punkt przerwania, w którym chcesz obserwować zachowanie obiektu.  W poprzednim kodzie, który będzie mieć `DoSomething()` metody.  
  
6.  Kontynuuj debugowanie i zatrzymania wykonywania w `DoSomething()` metody **Obejrzyj** jest wyświetlana w oknie `Person` obiektu.  
  
> [!NOTE]
>  Jeśli chcesz wyświetlić właściwości tego obiektu, takie jak `Person.Name` w powyższym przykładzie muszą mieć włączone właściwości oceny.  
  
## <a name="using-registers-in-the-watch-window-c-only"></a>Korzystanie z rejestrów w okno czujki (tylko C++)  
 Jeśli debugujesz kod macierzysty, można dodać nazwy rejestru, a także nazw zmiennych, przy użyciu  **$ \<zarejestrować nazwę >** lub  **@ \<zarejestrować nazwę >**.  Aby uzyskać więcej informacji, zobacz [Pseudozmienne](../debugger/pseudovariables.md).  
  
## <a name="dynamic-view-and-the-watch-window"></a>Dynamiczny widok i w oknie czujki  
 Niektóre języki skryptów (na przykład, JavaScript lub Python) Użyj dynamicznych lub [kaczka wpisując](https://en.wikipedia.org/wiki/Duck_typing), i językami .NET (w wersji 4.0 lub nowszy) obsługuje obiekty, które są trudne do obserwowania przy użyciu normalnych debugowania systemu windows, ponieważ ich może to być środowiska uruchomieniowego, właściwości i metody, które nie mogą być wyświetlane.  
  
 Gdy okno czujki wyświetla obiekt, który został utworzony na podstawie typu, który implementuje <xref:System.Dynamic.IDynamicMetaObjectProvider>, debuger dodaje specjalny **dynamiczny widok** węzeł, aby **Autos** wyświetlania. Ten węzeł zawiera dynamiczne elementy członkowskie obiektu dynamicznego, ale nie zezwala na edytowanie wartości elementów członkowskich.  
  
 Kliknięcie prawym przyciskiem myszy w dowolnym podrzędnym **dynamiczny widok** i wybierz polecenie **Dodaj czujkę**, debuger Wstawia nową zmienną watch, który rzutuje obiektu obiekt dynamiczny. Innymi słowy **nazwa obiektu** staje się (**obiekt (dynamiczny)). Nazwa**.  
  
 Ocena członków **dynamiczny widok** mogą mieć skutki uboczne. Opis efekty uboczne są znaleźć [efekty uboczne i wyrażenia](#bkmk_sideEffects). Dla języka C# debuger nie automatycznie Oblicz ponownie wartości widocznych na **dynamiczny widok** po kroku do nowego wiersza kodu. Dla języka Visual Basic wyrażeń dodane za pomocą **dynamiczny widok** są automatycznie odświeżane.  
  
 Aby uzyskać instrukcje na temat odświeżania wartości dynamiczny widok, zobacz [wartości odświeżanie wyrażenie kontrolne, które są nieaktualne](#bkmk_refreshWatch).  
  
 Jeśli chcesz wyświetlić tylko **dynamiczny widok** dla obiektu, możesz użyć **dynamiczne** specyfikatora formatu:  
  
-   C#: **ObjectName dynamiczne**  
  
-   Visual Basic:: **$dynamic, nazwa obiektu**  
  
 **Dynamiczny widok** również poprawia środowisko debugowania dla obiektów COM. Jeśli debuger napotka zapakowane w obiekt COM **.__ComObject**, dodaje **dynamiczny widok** węzła dla obiektu.  
  
## <a name="see-also"></a>Zobacz też  
 [Debuger Windows](../debugger/debugger-windows.md)
