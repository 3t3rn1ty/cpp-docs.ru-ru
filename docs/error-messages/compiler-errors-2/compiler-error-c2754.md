---
title: Ошибка компилятора C2754 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2754
dev_langs:
- C++
helpviewer_keywords:
- C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67338d647ce1774699973b8f498da9a8887eff11
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095669"
---
# <a name="compiler-error-c2754"></a>Ошибка компилятора C2754

«Специализация»: частичная специализация не может иметь параметр зависимого шаблона, не являющегося типом

Выполнена попытка частично специализировать класс шаблона, который имеет параметр зависимого шаблона, не являющегося типом. Это не допускается.

Следующий пример приводит к возникновению ошибки C2754:

```
// C2754.cpp
// compile with: /c

template<class T, T t>
struct A {};

template<class T, int N>
struct B {};

template<class T> struct A<T,5> {};   // C2754
template<> struct A<int,5> {};   // OK
template<class T> struct B<T,5> {};   // OK
```