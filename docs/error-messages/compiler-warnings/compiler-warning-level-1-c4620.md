---
title: "Предупреждение компилятора (уровень 1) C4620 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4620"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4620"
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4620
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не найдена постфиксная форма "оператор \+\+" для типа "тип"; используется префиксная форма  
  
 Отсутствует постфиксный оператор инкремента, определенный для данного типа. Компилятор использовал перегруженный префиксный оператор.  
  
 Это предупреждение можно избежать, определив постфиксный оператор `++`. Создайте версию оператора `++` с двумя аргументами, как показано ниже:  
  
```  
// C4620.cpp // compile with: /W1 class A { public: A(int nData) : m_nData(nData) { } A operator++() { m_nData -= 1; return *this; } // A operator++(int) // { //    A tmp = *this; //    m_nData -= 1; //    return tmp; // } private: int m_nData; }; int main() { A a(10); ++a; a++;   // C4620 }  
```