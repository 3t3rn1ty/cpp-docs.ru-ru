---
title: Ошибка компилятора C3197 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3197
dev_langs:
- C++
helpviewer_keywords:
- C3197
ms.assetid: 4e385c3b-222e-425c-9612-46e83ed41650
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83003a1538496d98dcc29d7a9954a68fb19c920e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022647"
---
# <a name="compiler-error-c3197"></a>Ошибка компилятора C3197

«ключевое_слово»: может использоваться только в определениях

Ключевое слово был использован в объявлении, но допустим только в определении.

Следующий пример приводит к возникновению ошибки C3197:

```
// C3197.cpp
// compile with: /clr /c
ref struct R abstract;   // C3197
ref struct R abstract {};   // OK

public ref class MyObject;   // C3197
ref class MyObject;   // OK
public ref class MyObject {};   // OK
```