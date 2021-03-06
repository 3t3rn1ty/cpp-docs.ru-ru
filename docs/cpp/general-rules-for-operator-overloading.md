---
title: Общие правила перегрузки операторов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operator overloading [C++], rules
ms.assetid: eb2b3754-35f7-4832-b1da-c502893dc0c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c3064da609c8a81a6e264c7f46d37d4cd5681d1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107147"
---
# <a name="general-rules-for-operator-overloading"></a>Общие правила перегрузки операторов

Приведенные ниже правила накладывают ограничения на реализацию перегруженных операторов. Тем не менее, они не применяются к [новый](../cpp/new-operator-cpp.md) и [удалить](../cpp/delete-operator-cpp.md) операторы, которые рассматриваются отдельно.

- Не удается определить новые операторы, такие как **.**.

- Не допускается переопределение операторов применительно ко встроенным типам данных.

- Перегруженные операторы должны быть нестатической функцией-членом класса или глобальной функцией. Глобальная функция, которой требуется доступ к частным или защищенным членам класса, должна быть объявлена в качестве дружественной функции этого класса. Глобальная функция должна принимать хотя бы один аргумент, имеющий тип класса или перечисляемый тип либо являющийся ссылкой на тип класса или перечисляемый тип. Пример:

    ```cpp
    // rules_for_operator_overloading.cpp
    class Point
    {
    public:
        Point operator<( Point & );  // Declare a member operator
                                     //  overload.
        // Declare addition operators.
        friend Point operator+( Point&, int );
        friend Point operator+( int, Point& );
    };

    int main()
    {
    }
    ```

     В предыдущем примере кода оператор "меньше чем" объявляется как функция-член; однако операторы сложения объявляются как глобальные функции, имеющие дружественный доступ. Обратите внимание, что для каждого оператора можно предоставить несколько реализаций. Выше для оператора сложения предоставлены две реализации, обеспечивающие его коммутативность. Это так же, как и скорее всего, операторы, добавляющие `Point` для `Point`, **int** для `Point`, и т. д., могут быть реализованы.

- Операторы подчиняются правилам приоритета, группирования и числа операндов, определяемым их типичным использованием со встроенными типами. Таким образом, нет способа реализации «добавить 2 и 3 для объекта типа `Point`,» ожидается 2, чтобы добавить *x* координат и 3, добавляемых к *y* координации.

- Унарные операторы, объявленные как функции-члены, не принимают аргументов; при объявлении как глобальные функции они принимают один аргумент.

- Бинарные операторы, объявленные как функции-члены, принимают один аргумент; при объявлении как глобальные функции они принимают два аргумента.

- Если оператор можно использовать как унарный и бинарный оператор (__&__, __*__, __+__, и __-__), каждая из которых использует можно перегрузить отдельно.

- Перегруженные операторы не могут иметь аргументов по умолчанию.

- Все перегруженные операторы, кроме назначения (**оператор =**) наследуются производными классами.

- Первым аргументов операторов, перегруженных в виде функций-членов, всегда является тип класса объекта, для которого вызывается этот оператор (класса, в котором объявлен оператор, или класса, производного от этого класса). Для первого аргумента никакие преобразования не предоставляются.

Обратите внимание, что значение любого оператора можно полностью изменить. Включающий в себя значение взятия адреса (**&**), назначения (**=**) и операторы вызова функции. Кроме того, эквивалентность, на которую можно полагаться при использовании встроенных типов, может быть изменена при перегрузке операторов. Например, после полного вычисления следующие четыре оператора обычно эквивалентны:

```cpp
var = var + 1;
var += 1;
var++;
++var;
```

Для типов классов с перегруженными операторами на такую эквивалентность полагаться невозможно. Более того, некоторые из неявных требований, существующих при использовании этих операторов для базовых типов, для перегруженных операторов ослабляются. Например, оператора сложения и присваивания, **+=**, требуется левый операнд должен быть l значение при применении к базовым типам; есть такое требование отсутствует, при перегрузке оператора.

> [!NOTE]
> Для согласованности при определении перегруженных операторов рекомендуется следовать модели для встроенных типов. Если семантика перегруженного оператора существенно отличается от его значения в других контекстах, это может скорее запутывать ситуацию, чем приносить пользу.

## <a name="see-also"></a>См. также

[Перегрузка операторов](../cpp/operator-overloading.md)