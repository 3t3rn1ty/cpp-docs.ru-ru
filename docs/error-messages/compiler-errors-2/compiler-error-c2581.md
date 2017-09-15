---
title: "Ошибка компилятора C2581 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2581"
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип" : функция "operator \=" не может быть статической  
  
 Оператор присваивания \(`=`\) объявлен как `static`, что недопустимо.  Операторы присваивания не могут объявляться как `static`.  Для получения дополнительной информации см. [Пользовательские операторы](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2581.  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```