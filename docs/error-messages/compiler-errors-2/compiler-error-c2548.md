---
title: Ошибка компилятора C2548 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2548
dev_langs:
- C++
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4fd5087613466ecb483ad4ec28018c9321453ff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050517"
---
# <a name="compiler-error-c2548"></a>Ошибка компилятора C2548

«класс::член»: отсутствующий параметр по умолчанию для параметра параметр

Список параметров по умолчанию отсутствует параметр. Если указан параметр по умолчанию в любом месте в списке параметров, необходимо определить параметры по умолчанию для всех последующих параметров.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2548:

```
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```