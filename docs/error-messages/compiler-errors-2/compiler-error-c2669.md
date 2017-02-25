---
title: "Ошибка компилятора C2669 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2669"
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использование функции\-члена не разрешается в анонимном объединении  
  
 Анонимное объединение не может иметь функции\-члены.  
  
 Следующий пример приводит к возникновению ошибки C2669:  
  
```  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  
## См. также  
 [Анонимные объединения](../../misc/anonymous-unions.md)