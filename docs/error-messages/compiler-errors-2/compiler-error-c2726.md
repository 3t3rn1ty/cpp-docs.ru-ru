---
title: Ошибка компилятора C2726 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2726
dev_langs:
- C++
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e421839e75bcc570578d7c37eecc8ab076321d7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051279"
---
# <a name="compiler-error-c2726"></a>Ошибка компилятора C2726

gcnew может использоваться только для создания объекта управляемого типа или типа WinRT

Невозможно создать экземпляр собственного типа в куче сбора мусора.

В следующем примере показано возникновение ошибки C2726 и приводятся сведения по ее устранению.

```
// C2726.cpp
// compile with: /clr
using namespace System;
class U {};
ref class V {};
value class W {};

int main() {
   U* pU = gcnew U;    // C2726
   U* pU2 = new U;   // OK
   V^ p2 = gcnew V;   // OK
   W p3;   // OK

}
```
