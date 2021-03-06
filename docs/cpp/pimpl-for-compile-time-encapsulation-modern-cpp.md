---
title: Pimpl для инкапсуляции времени компиляции (современный C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83b01a58745185499ac02a254a207fac2779be26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059008"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Pimpl для инкапсуляции времени компиляции (современный C++)

*Pimpl идиому* — это современный C++ способ скрыть реализацию, чтобы свести к минимуму взаимозависимость и для отдельных интерфейсов. Pimpl — сокращение «указатель на реализацию.» Может уже быть знакомы с этой концепцией, но по-другому, например как Чеширский Кот или брандмауэр компилятора идиому она известна.

## <a name="why-use-pimpl"></a>Зачем использовать pimpl?

Вот, как pimpl идиому можно улучшить жизненный цикл разработки программного обеспечения:

- Минимизация компиляции зависимости.

- Разделение интерфейс и реализацию.

- Переносимость.

## <a name="pimpl-header"></a>Pimpl заголовка

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Pimpl идиому предотвращает каскадные перестроения и макеты непрочные объекта. Она хорошо подходит для (транзитивно) популярных типов.

## <a name="pimpl-implementation"></a>Реализация Pimpl

Определение `impl` класс в CPP-файле.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>Рекомендации

Рассмотрите возможность добавления поддержки для специализации замены не создающие исключения.

## <a name="see-also"></a>См. также

[Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)