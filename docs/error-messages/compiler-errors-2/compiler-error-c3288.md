---
title: Ошибка компилятора C3288 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3288
dev_langs:
- C++
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36412510efcedd765ad44b4aab61e6a7d64155fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079938"
---
# <a name="compiler-error-c3288"></a>Ошибка компилятора C3288

«Тип»: недопустимая Отмена типа дескриптора

Компилятор обнаружил недопустимое разыменование типа дескриптора. Можно разыменования дескриптора типа и назначить его ссылку. Дополнительные сведения см. в разделе [оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3288.

```
// C3288.cpp
// compile with: /clr
ref class R {};
int main() {
   *(System::Object^) nullptr;   // C3288

// OK
   (System::Object^) nullptr;   // OK
   R^ r;
   R% pr = *r;
}
```