---
title: Предупреждение компилятора (уровень 1) C4556 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- C4556
dev_langs:
- C++
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987e4dc3ba6aea7dcb01dc05cd94c45baced05b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211032"
---
# <a name="compiler-warning-level-1-c4556"></a>Предупреждение компилятора (уровень 1) C4556

> значение встроенного аргумента интерпретации "*значение*«выходит за пределы диапазона»*lowerbound* - *upperbound*"

## <a name="remarks"></a>Примечания

Встроенная функция, которая соответствует машинная команда. Машинная команда имеет фиксированное число бит для кодирования константы. Если *значение* находится вне допустимого диапазона, оно будет закодировано неправильно. Компилятор усекает дополнительных битов.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4556:

```cpp
// C4556.cpp
// compile with: /W1
// processor: x86 IPF
#include <xmmintrin.h>

void test()
{
   __m64 m;
   _m_pextrw(m, 5);   // C4556
}

int main()
{
}
```