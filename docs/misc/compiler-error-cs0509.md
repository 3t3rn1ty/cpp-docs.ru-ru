---
title: "Ошибка компилятора CS0509 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0509"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0509"
ms.assetid: dc113e03-7a01-489b-b886-51ee056fc96a
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS0509
"класс1": не может быть производным от запечатанного типа "класс2"  
  
 [Запечатанный](../Topic/sealed%20\(C%23%20Reference\).md) класс не может использоваться в качестве [базового](../Topic/base%20\(C%23%20Reference\).md). Структуры являются запечатанными по умолчанию.  
  
 Следующий пример приводит к возникновению ошибки CS0509:  
  
```  
// CS0509.cs // compile with: /target:library sealed public class clx {} public class cly : clx {}   // CS0509  
```