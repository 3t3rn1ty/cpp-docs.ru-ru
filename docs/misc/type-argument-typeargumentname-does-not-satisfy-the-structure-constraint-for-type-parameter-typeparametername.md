---
title: "Аргумент типа &quot;&lt;имя_аргумента_типа&gt;&quot; не удовлетворяет ограничению &quot;Structure&quot; для параметра типа &quot;&lt;имя_параметра_типа&gt;&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32105"
  - "bc32105"
helpviewer_keywords: 
  - "BC32105"
ms.assetid: 09e5a837-8afd-4360-86bd-157e53c47513
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Аргумент типа &quot;&lt;имя_аргумента_типа&gt;&quot; не удовлетворяет ограничению &quot;Structure&quot; для параметра типа &quot;&lt;имя_параметра_типа&gt;&quot;
Аргумент типа, указанный для универсального типа, не удовлетворяет ограничению типа значения для соответствующего параметра типа.  
  
 Список ограничений назначает требования на тип аргумента, передаваемого параметру типа. Если не включать определенный класс или интерфейс в список ограничений, то можно наложить общее требование, указав одно из приведенных ниже ограничений.  
  
-   Аргумент типа должен быть типом значения \(включая ограничение [Structure \(Visual Basic\)](http://msdn.microsoft.com/ru-ru/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)\).  
  
-   Аргумент типа должен быть ссылочным типом \(включая ограничение [Class \(Visual Basic\)](http://msdn.microsoft.com/ru-ru/0777c6e6-46bc-451b-ad70-57b49d4ef4f7)\).  
  
 Нельзя указывать оба ограничения, `Structure` и `Class`, для одного и того же параметра типа, а также указывать какой\-либо из них более одного раза.  
  
 **Идентификатор ошибки:** BC32105  
  
### Исправление ошибки  
  
-   Выберите аргумент типа любого типа значения.  
  
## См. также  
 [Универсальные типы в Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Типы значений и ссылочные типы](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Практическое руководство. Использование универсального класса](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)