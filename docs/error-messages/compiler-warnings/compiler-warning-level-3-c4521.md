---
title: "Предупреждение (уровень 3) C4521 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4521
dev_langs: C++
helpviewer_keywords: C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e42bccd9dbc99d1f0914b4242c05a49aaf58ed1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4521"></a>Предупреждение компилятора (уровень 3) C4521
«класс»: заданы несколько конструкторов копии  
  
 Класс имеет несколько конструкторов копии одного типа. Это сообщение является информационным; конструкторы можно вызвать в программе.  
  
 Используйте [предупреждение](../../preprocessor/warning.md) pragma, чтобы отключить это предупреждение.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4521.  
  
```  
// C4521.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A() { cout << "A's default constructor" << endl; }  
   A( A &o ) { cout << "A&" << endl; }  
   A( const A &co ) { cout << "const A&" << endl; }   // C4521  
};  
  
int main() {  
   A o1;         // Calls default constructor.  
   A o2( o1 );   // Calls A( A& ).  
   const A o3;   // Calls default constructor.  
   A o4( o3 );   // Calls A( const A& ).  
}  
```