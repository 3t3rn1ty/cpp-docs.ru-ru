---
title: "Ошибка компилятора C3277 | Microsoft Docs"
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
  - "C3277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3277"
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

невозможно определить неуправляемый enum "перечисление" в пределах управляемого "тип"  
  
 Недопустимое определение перечисления в пределах управляемого типа.  
  
 Следующий пример приводит к возникновению ошибки C3277:  
  
```  
// C3277a.cpp  
// compile with: /clr  
ref class A  
{  
   enum E {e1,e2};   // C3277  
   // try the following line instead  
   // enum class E {e1,e2};  
};  
  
int main()  
{  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C3277:  
  
```  
// C3277b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class A  
{  
   enum E {e1,e2};   // C3277  
   // try the following line instead  
   // __value enum E {e1,e2};  
};  
  
int main()  
{  
}  
```