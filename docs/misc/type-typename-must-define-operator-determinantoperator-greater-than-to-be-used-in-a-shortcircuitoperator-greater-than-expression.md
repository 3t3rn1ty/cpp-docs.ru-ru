---
title: "Тип &quot;&lt;имя_типа&gt;&quot; должен определять оператор &quot;&lt;оператор_определителя&gt;&quot; для использования в выражении &quot;&lt;оператор_сокращенной_обработки&gt;&quot;. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33035"
  - "vbc33035"
helpviewer_keywords: 
  - "BC33035"
ms.assetid: 50a0a39f-63cd-4100-aea9-91b5b6ab5bbf
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип &quot;&lt;имя_типа&gt;&quot; должен определять оператор &quot;&lt;оператор_определителя&gt;&quot; для использования в выражении &quot;&lt;оператор_сокращенной_обработки&gt;&quot;.
Оператор [Оператор AndAlso](../Topic/AndAlso%20Operator%20\(Visual%20Basic\).md) или [Оператор OrElse](../Topic/OrElse%20Operator%20\(Visual%20Basic\).md) использует операнды типа класса или структуры, когда этот класс или структура не определяет нужный оператор.  
  
 Так как вы не задаете оператор сокращенной обработки \(`AndAlso` или `OrElse`\) напрямую, необходимо задать соответствующий логический оператор и оператор определителя. В следующей таблице представлены необходимые операторы.  
  
|Оператор сокращенной обработки|Логический оператор|Оператор определителя|  
|------------------------------------|-------------------------|---------------------------|  
|`AndAlso`|[Оператор And](../Topic/And%20Operator%20\(Visual%20Basic\).md)|[Оператор IsFalse](../Topic/IsFalse%20Operator%20\(Visual%20Basic\).md)|  
|`OrElse`|[Оператор Or](../Topic/Or%20Operator%20\(Visual%20Basic\).md)|[Оператор IsTrue](../Topic/IsTrue%20Operator%20\(Visual%20Basic\).md)|  
  
 [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] использует эти логические операторы и операторы определителя, чтобы построить логику сокращенной обработки для `AndAlso` или `OrElse`. Чтобы это работало правильно, оба операнда и возвращаемое значение вашего определения `And` или `Or` должны быть типа класса или структуры, в которой вы определяете `And` или `Or`.  
  
 **Идентификатор ошибки:** BC33035  
  
### Исправление ошибки  
  
-   Определите операторы `And` и `IsFalse` или операторы `Or` и `IsTrue` в классе или структуре, используемой для типа операнда оператора `AndAlso` или `OrElse`. Убедитесь, что операнды для оператора `And` или `Or` имеют тип класса или структуры, в которой вы его определяете.  
  
## См. также  
 [Процедуры операторов](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Оператор Operator](../Topic/Operator%20Statement.md)   
 [Практическое руководство. Определение оператора](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [Практическое руководство. Определение оператора преобразования](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Логические и побитовые операторы в Visual Basic](../Topic/Logical%20and%20Bitwise%20Operators%20in%20Visual%20Basic.md)