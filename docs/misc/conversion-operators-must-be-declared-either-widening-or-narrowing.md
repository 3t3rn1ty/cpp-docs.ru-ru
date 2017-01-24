---
title: "Операторы преобразования должны быть объявлены как Widening или Narrowing. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc33017"
  - "bc33017"
helpviewer_keywords: 
  - "BC33017"
ms.assetid: 5972d955-ce1d-4348-a021-167eecb3a507
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Операторы преобразования должны быть объявлены как Widening или Narrowing.
Оператор [Оператор Operator](../Topic/Operator%20Statement.md) не указывает ни [Widening](../Topic/Widening%20\(Visual%20Basic\).md), ни [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md).  
  
 При определении оператора преобразования необходимо объявить его как `Widening` или `Narrowing`. Это взаимно исключающие характеристики, поэтому их нельзя указывать обе.  
  
 **Идентификатор ошибки:** BC33017  
  
### Исправление ошибки  
  
-   Решите, должен ли оператор преобразования быть `Widening` или `Narrowing`, и включите соответствующее ключевое слово в оператор `Operator`. Необходимо указать то или другое ключевое слово.  
  
## См. также  
 [Расширяющие и сужающие преобразования](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [Процедуры операторов](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Оператор Operator](../Topic/Operator%20Statement.md)   
 [Практическое руководство. Определение оператора](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [Практическое руководство. Определение оператора преобразования](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)