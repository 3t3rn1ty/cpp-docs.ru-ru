---
title: Ошибка компилятора C2874 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2874
dev_langs:
- C++
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da285053507865d88fef31fac485c2a77a918d52
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031097"
---
# <a name="compiler-error-c2874"></a>Ошибка компилятора C2874

с помощью объявление вызвало наличие нескольких объявлений для «символ»

Объявление вызывает один и тот же элемент определяется два раза.

Следующий пример приводит к возникновению ошибки C2874:

```
// C2874.cpp
namespace Z {
   int i;
}

int main() {
   int i;
   using Z::i;   // C2874, i already declared
}
```