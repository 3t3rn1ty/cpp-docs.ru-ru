---
title: Ошибки компилятора с C2600 по C2699 | Документы Microsoft
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2604
- C2606
- C2607
- C2608
- C2609
- C2610
- C2615
- C2618
- C2620
- C2621
- C2622
- C2623
- C2625
- C2629
- C2631
- C2639
- C2641
- C2642
- C2643
- C2644
- C2684
- C2685
- C2686
- C2697
helpviewer_keywords:
- C2604
- C2606
- C2607
- C2608
- C2609
- C2610
- C2615
- C2618
- C2620
- C2621
- C2622
- C2623
- C2625
- C2629
- C2631
- C2639
- C2641
- C2642
- C2643
- C2644
- C2684
- C2685
- C2686
- C2697
dev_langs:
- C++
ms.assetid: 73c6319f-cbea-4a2f-913b-90dc1af61f64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0637ff146ca71c1ee14c534792cf70c44c0616b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283358"
---
# <a name="compiler-errors-c2600-through-c2699"></a>Ошибки компилятора с C2600 по C2699

Статьи в этом разделе документации объясняется подмножество сообщения об ошибках, которые создаются компилятором.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Сообщения об ошибках

|Ошибка|Сообщение|
|-----------|-------------|
|[Ошибка компилятора C2600](compiler-error-c2600.md)|"*функция*": не удается определить компилятором специальную функцию-член (должен быть объявлен в классе сначала)|
|[Ошибка компилятора C2601](compiler-error-c2601.md)|"*функция*": недопустимые локальные определения функций|
|[Ошибка компилятора C2602](compiler-error-c2602.md)|"*класса*::*идентификатор*«не является членом базового класса»*класс*"|
|[Ошибка компилятора C2603](compiler-error-c2603.md)|"*функция*": слишком много статических объектов блок области с конструкторами и деструкторами в функции|
|C2604 ошибки компилятора|"*идентификатор*": невозможно реализовать более одного метода интерфейса|
|[Ошибка компилятора C2605](compiler-error-c2605.md)|"*идентификатор*": этот метод зарезервирован в классе managed WinRT|
|C2606 ошибки компилятора|"*class1*": невозможно заново реализовать "*член*«, как он наследуется от базовой среды выполнения»*class2*"|
|C2607 ошибки компилятора|не удалось выполнить статическое объявление|
|C2608 ошибки компилятора|Является устаревшей.|
|C2609 ошибки компилятора|Является устаревшей.|
|C2610 ошибки компилятора|"*класса*::*член*": не является специальную функцию-член которого можно установить по умолчанию|
|[Ошибка компилятора C2611](compiler-error-c2611.md)|"*маркера*": недопустимый следующий "~" (Ожидался идентификатор)|
|[Ошибка компилятора C2612](compiler-error-c2612.md)|в конце "*символ*" недопустим в списке инициализаторов членов и базовых|
|[Ошибка компилятора C2613](compiler-error-c2613.md)|в конце "*символ*" недопустим в списке базовых классов|
|[Ошибка компилятора C2614](compiler-error-c2614.md)|"*класса*": недопустимая инициализация члена: "*идентификатор*" не является базовым классом или членом|
|C2615 ошибки компилятора|Является устаревшей.|
|[Ошибка компилятора C2616](compiler-error-c2616.md)|"*преобразования*": не удается неявно преобразовать не являющегося lvalue "*тип1*" для "*тип2*", не являющееся константным|
|[Ошибка компилятора C2617](compiler-error-c2617.md)|"*функция*": несовместимый оператор return|
|C2618 ошибки компилятора|Является устаревшей.|
|[Ошибка компилятора C2619](compiler-error-c2619.md)|"*идентификатор*": статические данные-член не допускается в анонимной структуре или объединении|
|Ошибка компилятора C2620|Является устаревшей.|
|Ошибка компилятора C2621|Является устаревшей.|
|Ошибка компилятора C2622|Является устаревшей.|
|Ошибка компилятора C2623|Является устаревшей.|
|[Ошибка компилятора C2624](compiler-error-c2624.md)|"*область*::*типа*": локальные классы не может использоваться для объявления переменных «extern»|
|Ошибка C2625 компилятора|"*идентификатор*": Недопустимый член объединения; тип "*типа*" является ссылочным типом|
|[Ошибка компилятора C2626](compiler-error-c2626.md)|"*идентификатор*": закрытые и защищенные данные-член не допускается в анонимной структуре или объединении|
|[Ошибка компилятора C2627](compiler-error-c2627.md)|"*функция*": функция-член не разрешается в анонимном объединении|
|[Ошибка компилятора C2628](compiler-error-c2628.md)|"*тип1*«следуют»*тип2*" является недопустимым (возможно, вы забыли «;»?)|
|C2629 ошибки компилятора|"*идентификатор*": анонимной структуре или объединении не может объявлять вложенный тип|
|[Ошибка компилятора C2630](compiler-error-c2630.md)|"*символ*" найден в том, что должен быть список с разделителями запятыми|
|C2631 ошибки компилятора|"*идентификатор*": класс или перечисление нельзя определить в шаблоне псевдонима|
|[Ошибка компилятора C2632](compiler-error-c2632.md)|"*тип1*«следуют»*тип2*" не допускается|
|[Ошибка компилятора C2633](compiler-error-c2633.md)|"*идентификатор*": «inline» является единственным допустимым классом хранения для конструкторов|
|[Ошибка компилятора C2634](compiler-error-c2634.md)|"*класса*::*член*": недопустимый указатель на ссылочный член|
|[Ошибка компилятора C2635](compiler-error-c2635.md)|не удается преобразовать "*тип1*\*" для "*тип2*\*"; предполагается преобразование из виртуального базового класса|
|[Ошибка компилятора C2636](compiler-error-c2636.md)|"*идентификатор*": недопустимый указатель на ссылочный член|
|[Ошибка компилятора C2637](compiler-error-c2637.md)|"*идентификатор*": нельзя изменять указатели на члены данных|
|[Ошибка компилятора C2638](compiler-error-c2638.md)|"*идентификатор*": модификатор __based недопустим для указателя на член|
|C2639 ошибки компилятора|Является устаревшей.|
|[Ошибка компилятора C2640](compiler-error-c2640.md)|"*идентификатор*": модификатор __based недопустим для ссылки|
|C2641 ошибки компилятора|Является устаревшей.|
|C2642 ошибки компилятора|Является устаревшей.|
|C2643 ошибки компилятора|Является устаревшей.|
|C2644 ошибки компилятора|Является устаревшей.|
|[Ошибка компилятора C2645](compiler-error-c2645.md)|отсутствует полное имя для указателя на член (найдено ":: *")|
|[Ошибка компилятора C2646](compiler-error-c2646.md)|анонимные структуры или объединения в глобальной или области видимости пространства имен необходимо объявлять как статическое|
|[Ошибка компилятора C2647](compiler-error-c2647.md)|"*оператор*": Невозможно разыменовать "*тип1*" на "*тип2*"|
|[Ошибка компилятора C2648](compiler-error-c2648.md)|"*идентификатор*": использование члена, как параметр по умолчанию должен быть статическим|
|[Ошибка компилятора C2649](compiler-error-c2649.md)|"*идентификатор*": не является «класса, структуры или объединения»|
|[Ошибка компилятора C2650](compiler-error-c2650.md)|"*оператор*": не может быть виртуальной функцией|
|[Ошибка компилятора C2651](compiler-error-c2651.md)|"*типа*": выражение слева от "::" должен быть класс, структура или объединение|
|[Ошибка компилятора C2652](compiler-error-c2652.md)|"*идентификатор*": недопустимый конструктор копии: первый параметр не должен быть "*типа*"|
|[Ошибка компилятора C2653](compiler-error-c2653.md)|"*идентификатор*": не является именем класса или пространства имен|
|[Ошибка компилятора C2654](compiler-error-c2654.md)|"*идентификатор*": попытка обращения к члену вне функции-члена|
|[Ошибка компилятора C2655](compiler-error-c2655.md)|"*идентификатор*': определение или повторное объявление недопустимые в текущей области|
|[Ошибка компилятора C2656](compiler-error-c2656.md)|"*функция*": функция не допускается в качестве битового поля|
|[Ошибка компилятора C2657](compiler-error-c2657.md)|"*класса*:: *" в начале оператора (забыли указать тип?)|
|[Ошибка компилятора C2658](compiler-error-c2658.md)|"*идентификатор*": переопределение в анонимной структуре или объединении|
|[Ошибка компилятора C2659](compiler-error-c2659.md)|"*оператор*": функция в качестве левого операнда|
|[Ошибка компилятора C2660](compiler-error-c2660.md)|"*функция*": функция не принимает *номер* аргументов|
|[Ошибка компилятора C2661](compiler-error-c2661.md)|"*функция*": нет перегруженной функции, принимающей *номер* аргументов|
|[Ошибка компилятора C2662](compiler-error-c2662.md)|"*функция*": не удается преобразовать указатель «this» из "*тип1*«to»*тип2*"|
|[Ошибка компилятора C2663](compiler-error-c2663.md)|"*функция*": *номер* перегрузки имеют нет допустимого преобразования для указатель «this»|
|[Ошибка компилятора C2664](compiler-error-c2664.md)|"*функция*": не удается преобразовать аргумент *номер* из "*тип1*«to»*тип2*"|
|[Ошибка компилятора C2665](compiler-error-c2665.md)|"*функция*": ни один из *номер* перегрузки удалось преобразовать все типы аргументов|
|[Ошибка компилятора C2666](compiler-error-c2666.md)|"*функция*": *номер* перегрузок есть подобные преобразования|
|[Ошибка компилятора C2667](compiler-error-c2667.md)|"*функция*": ни один из *номер* перегрузок нет наилучшего преобразования|
|[Ошибка компилятора C2668](compiler-error-c2668.md)|"*функция*": неоднозначный вызов перегруженной функции|
|[Ошибка компилятора C2669](compiler-error-c2669.md)|функции-члена не разрешается в анонимном объединении|
|[Ошибка компилятора C2670](compiler-error-c2670.md)|"*функция*": шаблон функции не удалось конвертировать параметр *номер* из типа "*типа*"|
|[Ошибка компилятора C2671](compiler-error-c2671.md)|"*функция*": статические функции-члены не имеют указателей «this»|
|[C2672 ошибки компилятора](compiler-error-c2672.md)|"*функция*": нет соответствующего перегруженная функция найдена|
|[Ошибка компилятора C2673](compiler-error-c2673.md)|"*функция*": глобальные функции не имеют указателей «this»|
|[Ошибка компилятора C2674](compiler-error-c2674.md)|универсальное объявление не допускается в этом контексте|
|[Ошибка компилятора C2675](compiler-error-c2675.md)|унарный "*оператор*": "*типа*" не определяет этот оператор или преобразование к типу приемлемо к встроенному оператору|
|[Ошибка компилятора C2676](compiler-error-c2676.md)|двоичный "*оператор*": "*типа*" не определяет этот оператор или преобразование к типу приемлемо к встроенному оператору|
|[Ошибка компилятора C2677](compiler-error-c2677.md)|двоичный "*оператор*": не найден глобальный оператор которого принимает тип "*типа*" (или приемлемое преобразование отсутствует)|
|[Ошибка компилятора C2678](compiler-error-c2678.md)|двоичный "*оператор*": не найден оператор, принимающий левый операнд типа "*типа*" (или приемлемое преобразование отсутствует)|
|[Ошибка компилятора C2679](compiler-error-c2679.md)|двоичный "*оператор*": не найден оператор, принимающий правый операнд типа "*типа*" (или приемлемое преобразование отсутствует)|
|[Ошибка компилятора C2680](compiler-error-c2680.md)|"*тип*": недопустимый тип целевого объекта для *приведения*|
|[Ошибка компилятора C2681](compiler-error-c2681.md)|"*тип*": недопустимый тип выражения для *приведения*|
|[Ошибка компилятора C2682](compiler-error-c2682.md)|нельзя использовать "*приведения*«для преобразования из»*тип1*«to»*тип2*"|
|[Ошибка компилятора C2683](compiler-error-c2683.md)|"*приведения*": "*типа*" не является полиморфным типом|
|C2684 ошибки компилятора|"*декларатор*": deleted и установленные по умолчанию функции не поддерживаются в классах managed WinRT|
|C2685 ошибки компилятора|"*декларатор*": функции, удалять и установленные по умолчанию не поддерживаются с явными описателями ограничений|
|C2686 ошибки компилятора|Невозможно перегрузить функции-члены статических и нестатических с теми же типами параметров|
|[Ошибка компилятора C2687](compiler-error-c2687.md)|"*типа*": объявление исключения не может быть «void» и не может обозначать неполный тип, указатель или ссылку на неполный тип|
|[Ошибка компилятора C2688](compiler-error-c2688.md)|"*тип*::*член*": ковариантные возвращаемые значения с несколькими или виртуальными наследованиями не поддерживаются для функций varargs|
|[Ошибка компилятора C2689](compiler-error-c2689.md)|"*функция*": дружественную функцию нельзя определить в пределах локального класса|
|[Ошибка компилятора C2690](compiler-error-c2690.md)|"*оператор*": невозможно выполнять арифметические операции в массиве управляемых WinRT|
|[Ошибка компилятора C2691](compiler-error-c2691.md)|"*типа*": массив managed WinRT не может содержать элементы этого типа|
|[Ошибка компилятора C2692](compiler-error-c2692.md)|"*функция*": компилятора C необходимы полные прототипы функций "/ clr" параметр|
|[Ошибка компилятора C2693](compiler-error-c2693.md)|"*оператор*": недопустимое сравнение для ссылок на массив managed WinRT|
|[Ошибка компилятора C2694](compiler-error-c2694.md)|"*переопределяющая_функция*": переопределяющая виртуальная функция обладает менее ограниченной спецификацией исключений, чем базовая виртуальная функция-член "*базовая_функция*"|
|[Ошибка компилятора C2695](compiler-error-c2695.md)|"*переопределяющая_функция*": переопределение виртуальной функции отличается от "*базовая_функция*" только соглашением о вызове|
|[Ошибка компилятора C2696](compiler-error-c2696.md)|Не удается создать временный объект типа managed WinRT "*типа*"|
|Ошибка компилятора C2697|Является устаревшей.|
|[Ошибка компилятора C2698](compiler-error-c2698.md)|объявление using для "*объявление1*«не могут сосуществовать с существующие объявление using для»*объявление2*"|
