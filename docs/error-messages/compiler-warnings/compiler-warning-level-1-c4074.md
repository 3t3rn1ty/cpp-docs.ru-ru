---
title: Предупреждение (уровень 1) C4074 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4074
dev_langs:
- C++
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9072728660ca78097a1e36e492670a614bb2b2f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4074"></a>Предупреждение (уровень 1) C4074 компилятора
инициализаторы в зарезервированной области инициализации компилятора  
  
 Область инициализации компилятора, которая задана в [#pragma init_seg](../../preprocessor/init-seg.md), зарезервирован корпорацией Майкрософт. Код в этой области может быть выполнена до инициализации библиотеки времени выполнения C.  
  
 Следующий пример приводит к возникновению ошибки C4074:  
  
```  
// C4074.cpp  
// compile with: /W1  
#pragma init_seg( compiler )   // C4074  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```