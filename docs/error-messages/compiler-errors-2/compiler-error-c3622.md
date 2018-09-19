---
title: Ошибка компилятора C3622 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13ba39a2baf9da2039bbc97fe459f8840effacea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062414"
---
# <a name="compiler-error-c3622"></a>Ошибка компилятора C3622

«класс»: класс, объявленный как «ключевое_слово» не может быть создан

Была предпринята попытка создать экземпляр класса, помеченного как [абстрактный](../../windows/abstract-cpp-component-extensions.md). Класс, помеченный как `abstract` может быть базовым классом, но он не может быть создан.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3622.

```
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
