---
title: "Ошибка компилятора C2279 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2279
dev_langs:
- C++
helpviewer_keywords:
- C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6523db90f1d934c6c7cd715ed5fbd3b7d8ab64c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2279"></a>Ошибка компилятора C2279
Спецификация исключения не может использоваться в объявлении typedef  
  
 В разделе **/Za**, [спецификации исключений](../../cpp/exception-specifications-throw-cpp.md) не допускается в объявлении typedef.  
  
 Следующий пример приводит к возникновению ошибки C2279:  
  
```  
// C2279.cpp  
// compile with: /Za /c  
typedef int (*xy)() throw(...);   // C2279  
typedef int (*xyz)();   // OK  
```
