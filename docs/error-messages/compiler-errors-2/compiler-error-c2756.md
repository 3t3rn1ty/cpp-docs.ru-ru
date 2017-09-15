---
title: "Ошибка компилятора C2756 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2756"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2756"
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2756
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип шаблона": применение аргументов шаблона по умолчанию в частичной специализации не разрешается  
  
 Шаблон для частичной специализации не может содержать аргумент по умолчанию.  
  
 В следующем примере показано возникновение ошибки C2756 и приводятся сведения по ее устранению.  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```