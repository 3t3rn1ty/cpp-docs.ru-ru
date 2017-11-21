---
title: "Ошибка компилятора C3652 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3652
dev_langs: C++
helpviewer_keywords: C3652
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4bade460d97b8d7dcb38e7d37fa87f2910047c47
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3652"></a>Ошибка компилятора C3652
«override»: явно переопределяющая функция должна быть виртуальной  
  
 Функция, которая явно переопределяет должна быть виртуальной. Дополнительные сведения см. в разделе [явное переопределение](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3652:  
  
```  
// C3652.cpp  
// compile with: /clr /c  
public interface class I {  
   void f();  
};  
  
public ref struct R : I {  
   void f() = I::f {}   // C3652  
   // try the following line instead  
   // virtual void f() = I::f {}  
};  
```