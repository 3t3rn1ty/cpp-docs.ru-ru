---
title: "Ошибка компилятора C3711 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3711"
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метод": типом возвращаемого значения метода неуправляемого источника события должен быть void или целочисленный тип  
  
 В источнике события определен метод, тип возвращаемого значения которого не является целочисленным типом или типом void.  Чтобы устранить эту ошибку, измените событие и обработчик событий так, чтобы в качестве типа возвращаемого значения в них использовался тип `void` или целочисленный тип, например `int` или `long`.  
  
 Следующий пример приводит к возникновению ошибки C3711:  
  
```  
// C3711.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[event_source(native)]  
class CEventSrc {  
public:  
   __event float event1();   // C3711  
   // try the following line instead  
   // __event int event1();  
   // also change the handler, below  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   float handler1() {         // change float to int  
      return 0.0;             // change 0.0 to 0  
   }  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
  
int main() {  
}  
```