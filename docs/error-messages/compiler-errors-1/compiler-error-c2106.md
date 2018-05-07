---
title: Ошибка компилятора C2106 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2106
dev_langs:
- C++
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0d8b55bed4b86e44ada9f81dc2bf0269af604ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2106"></a>Ошибка компилятора C2106
«оператор»: левый операнд должен быть l значение  
  
 Как левый операнд оператора должен иметь l значением.  
  
 Следующий пример приводит к возникновению ошибки C2106:  
  
```  
// C2106.cpp  
int main() {  
   int a;  
   1 = a;   // C2106  
   a = 1;   // OK  
}  
```