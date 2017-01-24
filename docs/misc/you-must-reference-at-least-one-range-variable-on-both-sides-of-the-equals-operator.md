---
title: "Необходима ссылка по крайней мере на одну переменную диапазона с обеих сторон оператора &quot;equals&quot; | Microsoft Docs"
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
  - "vbc36622"
  - "bc36622"
helpviewer_keywords: 
  - "BC36622"
ms.assetid: 8d301227-131d-4977-b3ff-1fc4e427f8fa
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Необходима ссылка по крайней мере на одну переменную диапазона с обеих сторон оператора &quot;equals&quot;
Вы должны сослаться по крайней мере на одну переменную диапазона с обеих сторон оператора "equals". Хотя бы одна переменная диапазона \<переменные\> должна быть с одной стороны оператора "equals", и хотя бы одна переменная диапазона \<переменные\> должна быть с другой стороны.  
  
 Переменные диапазона, определенные для коллекций, которые будут присоединены в запросе LINQ, должны быть по разные стороны оператора `Equals`, в зависимости от коллекции, для которой они определены. То есть переменные диапазона, определенные для одной из присоединяемых коллекций, должны быть на противоположной стороне оператора `Equals` от переменных диапазона для других присоединяемых коллекций. Переменные диапазона из отдельных коллекций нельзя смешивать на одной стороне оператора `Equals`.  
  
 На каждой стороне оператора `Equals` должна быть ссылка хотя бы на одну переменную из каждой присоединяемой коллекции.  
  
 **Идентификатор ошибки:** BC36622  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)   
 [Предложение Join](../Topic/Join%20Clause%20\(Visual%20Basic\).md)   
 [Предложение Group Join](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [Предложение From](../Topic/From%20Clause%20\(Visual%20Basic\).md)   
 [Предложение Select](../Topic/Select%20Clause%20\(Visual%20Basic\).md)