---
title: Ошибка компилятора C2787 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4096e5dbd5b885afe3dec136a111ec69a10784f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109136"
---
# <a name="compiler-error-c2787"></a>Ошибка компилятора C2787

«Идентификатор»: идентификатор GUID не была связана с этим объектом

[__Uuidof](../../cpp/uuidof-operator.md) оператор принимает определяемого пользователем типа с присоединенным идентификатором GUID или объект такого типа определяемых пользователем. Эта ошибка возникает, если аргумент является определяемый пользователем тип не сопоставлен идентификатор GUID.

Следующий пример приводит к возникновению ошибки C2787:

```
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```