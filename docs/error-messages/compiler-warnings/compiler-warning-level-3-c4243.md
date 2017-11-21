---
title: "Предупреждение (уровень 3) C4243 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4243
dev_langs: C++
helpviewer_keywords: C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 527dbbc55fca3f8c602704472ba17a31d54b4b3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4243"></a>Предупреждение компилятора (уровень 3) C4243
Тип преобразования: преобразование из «тип1» в «тип2» существует, но недоступно  
  
 Указатель на производный класс преобразуется в указатель на базовый класс, но производный класс наследует базовый класс с доступа private или protected.  
  
 Следующий пример приводит к возникновению ошибки C4243:  
  
```  
// C4243.cpp  
// compile with: /W3  
// C4243 expected  
struct B {  
   int f() {  
      return 0;  
   };  
};  
  
struct D : private B {};  
struct E : public B {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   int (D::* d)() = (int(D::*)()) &B::f;   
   d;  
  
   int (E::* e)() = (int(E::*)()) &B::f; // OK  
   e;  
}  
```