---
title: "Практическое руководство. Реагирование на изменения в UML-модели | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0300371-9cac-4def-a3f5-7d7b62dcd6f3
caps.latest.revision: 3
caps.handback.revision: 3
author: "alancameronwills"
ms.author: "awills"
manager: "kamrani"
---
# Практическое руководство. Реагирование на изменения в UML-модели
Можно написать код, который будет выполняться при возникновении изменений в модели UML в Visual Studio.  Такой код будет одинаково реагировать на изменения, внесенные самими пользователями, и на изменения, внесенные другими расширениями Visual Studio .  Чтобы узнать, какие версии Visual Studio поддерживают модели UML, см. раздел [Поддержка версий для инструментов моделирования и архитектуры](../Topic/What's%20new%20for%20design%20in%20Visual%20Studio.md#VersionSupport).  
  
> [!WARNING]
>  API UML эти методы не поддерживает.  В будущих версиях Visual Studio они также могут не работать.  
  
 Образец кода см. в разделе [UML: отклик на изменения в модели UML с использованием событий и правил](http://code.msdn.microsoft.com/UML-Responding-to-changes-c024cd4b)  
  
## См. также  
 [Навигация по модели UML](../Topic/Navigate%20the%20UML%20model.md)   
 [Обработчики событий распространяют изменения за пределы модели](../Topic/Event%20Handlers%20Propagate%20Changes%20Outside%20the%20Model.md)   
 [Пример: цвет по стереотипам](http://go.microsoft.com/fwlink/?LinkId=213841)