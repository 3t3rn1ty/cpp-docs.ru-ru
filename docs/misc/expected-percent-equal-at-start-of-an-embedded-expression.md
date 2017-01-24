---
title: "Ожидался элемент &quot;%=&quot; в начале внедренного выражения. | Microsoft Docs"
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
  - "vbc31179"
  - "bc31179"
helpviewer_keywords: 
  - "BC31179"
ms.assetid: 20b0382e-1744-47e4-84e1-7fc926cbc4df
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ожидался элемент &quot;%=&quot; в начале внедренного выражения.
Начальный идентификатор для внедренного выражения `<%=` не был закодирован правильно. Обратите внимание, что нельзя использовать символ процента \(%\) в литерале XML\-элемента.  
  
 **Идентификатор ошибки:** BC31179  
  
### Исправление ошибки  
  
-   Убедитесь, что начальный идентификатор для внедренного выражения закодирован как `<%=`.  
  
## См. также  
 [Встроенные выражения в XML](../Topic/Embedded%20Expressions%20in%20XML%20\(Visual%20Basic\).md)   
 [XML\-литералы](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)