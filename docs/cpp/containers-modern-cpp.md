---
title: Контейнеры (современный C++) | Документация Майкрософт
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a05eada2b5828cfc654496355bddcabcafc8d60
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086152"
---
# <a name="containers-modern-c"></a>Контейнеры (современный C++)

По умолчанию используют [вектор](../standard-library/vector-class.md) как предпочтительный последовательный контейнер в C++. Это эквивалентно `List<T>` на языках .NET.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Используйте [карты](../standard-library/map-class.md) (не `unordered_map`) как в качестве ассоциативного контейнера по умолчанию. Используйте [задать](../standard-library/set-class.md), [мультиотображения](../standard-library/multimap-class.md), и [мультинабор](../standard-library/multiset-class.md) вырожденный & нескольких случаях.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Если необходима оптимизация производительности, рассмотрите возможность использования:

- [Массива](../standard-library/array-class-stl.md) введите при внедрении важно, например, как член класса.

- Неупорядоченные ассоциативные контейнеры, такие как [unordered_map](../standard-library/unordered-map-class.md). Они имеют нижний элемент издержки и поиск постоянного времени, но они могут быть сложнее использовать корректно и правильно.

- Отсортированные `vector`. Дополнительные сведения см. в разделе [Алгоритмы](../cpp/algorithms-modern-cpp.md).

Не используйте массивы в стиле C. Для более старых API, требующие прямого доступа к данным, используйте методы доступа, такие как `f(vec.data(), vec.size());` вместо этого.

Дополнительные сведения о контейнерах см. в разделе [контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

## <a name="see-also"></a>См. также

[Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)