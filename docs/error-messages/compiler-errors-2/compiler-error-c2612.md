---
title: "Ошибка компилятора C2612 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2612"
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимый завершающий "знак" в списке инициализаторов членов и базовых классов  
  
 Символ отображается после последнего базового класса или члена в списке инициализаторов.  
  
 Следующий пример приводит к возникновению ошибки C2612:  
  
```  
// C2612.cpp  
class A {  
public:  
   int i;  
   A( int ia ) : i( ia ) + {};   // C2612  
};  
```