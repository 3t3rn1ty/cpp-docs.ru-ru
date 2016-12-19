---
title: "Ошибка MSBuild MSB3252 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSB3252"
helpviewer_keywords: 
  - "MSB3252"
ms.assetid: 4e6982b8-84b3-4d21-94e1-05cc10bf1393
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Ошибка MSBuild MSB3252
**MSB3252. Проект содержит ссылку на сборку \<имя\>.  Эта сборка не входит в клиентский профиль платформы .NET Framework.  При отсутствии данной ссылки возможны ошибки компиляции или среды выполнения.**  
  
 Был сделан вызов элементу в сборке \(или зависимой сборке\), не являющейся частью подмножества [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)].  Поэтому вызов нельзя сопоставить, и выполнить компиляцию приложения невозможно.  
  
 Дополнительные сведения о веб\-службе [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] см. в разделе [Профиль клиента .NET Framework](../Topic/.NET%20Framework%20Client%20Profile.md).  
  
### Чтобы исправить эту ошибку  
  
-   Удалите из проекта ссылку на указанную сборку или выполните нацеливание на полную версию платформы [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] вместо библиотеки подмножества [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)].  Дополнительные сведения о нацеливании на полную версию платформы [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] см. в разделе [Практическое руководство. Определение целевой версии .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
## См. также  
 [Целевая рабочая среда и целевая платформа](../Topic/MSBuild%20Target%20Framework%20and%20Target%20Platform.md)   
 [Элемент Project \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Дополнительные ресурсы](../Topic/Additional%20MSBuild%20Resources.md)