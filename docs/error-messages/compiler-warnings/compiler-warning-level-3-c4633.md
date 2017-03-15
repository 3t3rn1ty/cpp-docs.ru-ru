---
title: "Предупреждение компилятора (уровень 3) C4633 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4633"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4633"
ms.assetid: 6d76f268-ba8c-448b-8e83-b903a18b583b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 3) C4633
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Конечный объект комментария в документе XML: ошибка: причина  
  
 Имя, переданное в тег [\<param\>](../Topic/%3Cparam%3E%20\(Visual%20C++\).md) не удалось обнаружить.  
  
 Следующий пример приводит к возникновению ошибки C4633:  
  
```  
// C4633.cpp  
// compile with: /clr /doc /LD /W3  
  
/// Text for class MyClass.  
public ref class MyClass {  
   // C4633 remove line for Int3  
   /// <param name="Int1">Used to indicate status.</param>  
   /// <param name="Int3">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
      Int1 = 0;  
      Int1++;  
   }  
};  
```