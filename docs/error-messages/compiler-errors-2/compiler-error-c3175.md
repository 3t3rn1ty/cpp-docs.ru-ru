---
title: "Ошибка компилятора C3175 | Microsoft Docs"
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
  - "C3175"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3175"
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3175
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция 1": невозможно вызвать метод управляемого типа из неуправляемой функции "функция 2"  
  
 Неуправляемые функции не могут вызвать функции членов управляемых классов.  
  
 Следующий пример приводит к возникновению ошибки C3175:  
  
```  
// C3175_2.cpp  
// compile with: /clr  
  
ref struct A {  
   static void func() {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2() {  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main() {  
   A ^a = gcnew A;  
   func2();  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C3175:  
  
```  
// C3175.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc struct A  
{  
   static void func()  
   {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2()  
{  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main()  
{  
   A *a = new A;  
   func2();  
}  
```