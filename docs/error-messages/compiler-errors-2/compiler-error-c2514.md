---
title: Ошибка компилятора C2514 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2514
dev_langs:
- C++
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 392c46224078c35df5ae02a88503726b193c87f3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085515"
---
# <a name="compiler-error-c2514"></a>Ошибка компилятора C2514

«класс»: класс не имеет конструкторов

Класс, структура или объединение не имеет конструктора со списком параметров, который соответствует параметрам, используемым для создания его экземпляра.

Класс должен объявляться полностью, прежде чем он может быть создан.

Следующий пример приводит к возникновению ошибки C2514:

```
// C2514.cpp
// compile with: /c
class f;

class g {
public:
    g (int x);
};

class fmaker {
   f *func1() {
      return new f(2);   // C2514
   }

   g *func2() {
      return new g(2);   // OK
   }
};
```