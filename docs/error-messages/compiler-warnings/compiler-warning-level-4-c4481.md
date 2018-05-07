---
title: Предупреждение (уровень 4) C4481 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4481
dev_langs:
- C++
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeef5f2121808c5444af942fac0e3b72919f2354
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4481"></a>Предупреждение компилятора (уровень 1) C4481
использовано нестандартное расширение: спецификатор переопределения «ключевое слово»  
  
 Ключевое слово использовалось, которого нет в стандарт языка C++, например, один из спецификаторов переопределения, которые также могут использоваться в/CLR.  Дополнительные сведения см. в следующих разделах:  
  
-   [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Спецификаторы переопределения](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4481.  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```