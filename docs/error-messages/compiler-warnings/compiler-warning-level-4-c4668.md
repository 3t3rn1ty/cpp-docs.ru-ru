---
title: Предупреждение компилятора (уровень 4) C4668 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4668
dev_langs:
- C++
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c960eb2cc79298977c8d7c91808b0a5492d05758
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074013"
---
# <a name="compiler-warning-level-4-c4668"></a>Предупреждение компилятора (уровень 4) C4668

"символ" не определен в качестве макроса препроцессора и будет заменен в "директивах" на "0"

Символ, который не был определен использовался в директиве препроцессора. Символ будет вычислять по false. Чтобы определить символ, можно использовать либо [#define директива](../../preprocessor/hash-define-directive-c-cpp.md) или [/D](../../build/reference/d-preprocessor-definitions.md) параметр компилятора.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4668:

```
// C4668.cpp
// compile with: /W4
#include <stdio.h>

#pragma warning (default : 4668)   // turn warning on

int main()
{
    #if q   // C4668, q is not defined
        printf_s("defined");
    #else
        printf_s("undefined");
    #endif
}
```