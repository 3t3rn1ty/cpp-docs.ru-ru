---
title: Предупреждение компилятора (уровень 4) C4918 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4918
dev_langs:
- C++
helpviewer_keywords:
- C4918
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb4cc66359c28ffc23afa64da1e5bdbaadd8fb9b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023232"
---
# <a name="compiler-warning-level-4-c4918"></a>Предупреждение компилятора (уровень 4) C4918

"символ": недопустимый символ в списке оптимизации директивы pragma

В списке оптимизации оператора прагмы [optimize](../../preprocessor/optimize.md) был найден неизвестный символ.

Например, следующий оператор приводит к созданию предупреждения C4918:

```
// C4918.cpp
// compile with: /W4
#pragma optimize("X", on) // C4918 expected
int main()
{
}
```