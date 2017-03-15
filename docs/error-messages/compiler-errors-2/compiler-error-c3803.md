---
title: "Ошибка компилятора C3803 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3803"
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

свойство: тип свойства несовместим с одной из функций доступа к нему "метод доступа"  
  
 Тип свойства, определяемого при помощи [property](../../cpp/property-cpp.md), не соответствует возвращаемому типу одной из функций его методов доступа.  
  
 Следующий пример приводит к возникновению ошибки C3803:  
  
```  
// C3803.cpp  
struct A  
{  
   __declspec(property(get=GetIt)) int i;  
   char GetIt()  
   {  
      return 0;  
   }  
  
   /*  
   // try the following definition instead  
   int GetIt()  
   {  
      return 0;  
   }  
   */  
}; // C3803  
  
int main()  
{  
}  
```