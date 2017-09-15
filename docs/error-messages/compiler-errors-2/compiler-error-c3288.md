---
title: "Ошибка компилятора C3288 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3288"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3288"
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3288
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : недопустимое разыменование типа дескриптора  
  
 Компилятор обнаружил недопустимое разыменование типа дескриптора.  Тип дескриптора можно разыменовать и назначить его ссылке.  Для получения дополнительной информации см. [Оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3288:  
  
```  
// C3288.cpp  
// compile with: /clr  
ref class R {};  
int main() {  
   *(System::Object^) nullptr;   // C3288  
  
// OK  
   (System::Object^) nullptr;   // OK  
   R^ r;  
   R% pr = *r;  
}  
```