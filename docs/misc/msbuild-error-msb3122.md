---
title: "Ошибка MSBuild MSB3122 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationsApplicationNotFullTrust"
helpviewer_keywords: 
  - "MSB3122"
ms.assetid: 523e4160-f165-437a-9f19-fb2ec77d46f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Ошибка MSBuild MSB3122
**MSB3122. Для использования сопоставления файлов требуется полное доверие.**  
  
 Для публикации приложения, настраивающего сопоставление файлов, оно должно быть приложением с полным доверием.  
  
### Чтобы исправить эту ошибку  
  
-   Включите параметры безопасности ClickOnce и сделайте приложение приложением с полным доверием.  Дополнительные сведения см. в разделе [Практическое руководство. Включение параметров безопасности ClickOnce\-приложений.](../Topic/How%20to:%20Enable%20ClickOnce%20Security%20Settings.md).  
  
## См. также  
 [Страница публикации в конструкторе проектов](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [Манифест приложения ClickOnce](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Управление доступом для кода для приложения ClickOnce](../Topic/Code%20Access%20Security%20for%20ClickOnce%20Applications.md)