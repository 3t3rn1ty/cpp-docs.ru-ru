---
title: "Ошибка компилятора C2361 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2361"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2361"
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2361
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

инициализация идентификатора 'identifier' пропущена меткой 'default'  
  
 Инициализация `identifier` может быть пропущена в операторе `switch`.  Нельзя перейти назад к объявлению с инициализатором, если только объявление не заключено в блок. \(Если только переменная не объявлена внутри блока, она находится в пределах области до конца оператора `switch`\).  
  
 Следующий пример приводит к возникновению ошибки C2361:  
  
```  
// C2361.cpp  
void func( void ) {  
   int x;  
   switch (x) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   default :   // C2361 error  
      int k = 1;  
   }  
}  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2361b.cpp  
// compile with: /c  
void func( void ) {  
   int x = 0;  
   switch (x) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   default :  
      int k = 1;  
   }  
}  
```