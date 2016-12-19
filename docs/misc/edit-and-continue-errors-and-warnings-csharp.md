---
title: "Ошибки и предупреждения режима &quot;Изменить и продолжить&quot; (C#) | Microsoft Docs"
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
  - "vs.csharp.enc.error_4001"
  - "vs.csharp.enc.error_4034"
  - "vs.csharp.enc.error_4003"
  - "vs.csharp.enc.error_4026"
  - "vs.csharp.enc.error_4032"
  - "vs.csharp.enc.error_4017"
  - "vs.csharp.enc.error_4053"
  - "vs.csharp.enc.error_4024"
  - "vs.csharp.enc.error_4012"
  - "vs.csharp.enc.error_4066"
  - "vs.csharp.enc.error_4020"
  - "vs.csharp.enc.error_4008"
  - "vs.csharp.enc.error_4033"
  - "vs.csharp.enc.error_4014"
  - "vs.csharp.enc.error_4023"
  - "vs.csharp.enc.error_4011"
  - "vs.csharp.enc.error_4006"
  - "vs.csharp.enc.error_4059"
  - "vs.csharp.enc.error_4015"
  - "vs.csharp.enc.error_4018"
  - "vs.csharp.enc.error_4028"
  - "vs.csharp.enc.error_4013"
  - "vs.csharp.enc.error_4009"
  - "vs.csharp.enc.error_4021"
  - "vs.csharp.enc.error_4065"
  - "vs.csharp.enc.error_4029"
  - "vs.csharp.enc.error_4058"
  - "vs.csharp.enc.error_4019"
  - "vs.csharp.enc.error_4007"
  - "vs.csharp.enc.error_4052"
  - "vs.csharp.enc.error_4025"
  - "vs.csharp.enc.error_4055"
  - "vs.csharp.enc.error_4022"
  - "vs.csharp.enc.error_4002"
  - "vs.csharp.enc.error_4016"
  - "vs.csharp.enc.error_4043"
  - "vs.csharp.enc.error_4027"
  - "vs.csharp.enc.error_4054"
  - "vs.csharp.enc.error_4004"
  - "vs.csharp.enc.error_4010"
  - "vs.csharp.enc.error_4030"
  - "vs.csharp.enc.error_4005"
  - "vs.csharp.enc.error_4035"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "Изменить и продолжить [C#], ошибки и предупреждения"
  - "ошибки [C#], отладка"
  - "ошибки [отладчик], Изменить и продолжить"
ms.assetid: c0e12b0a-8009-4a4a-979f-c804a91a5d9b
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "susanno"
manager: "douge"
---
# Ошибки и предупреждения режима &quot;Изменить и продолжить&quot; (C#)
Были внесены изменения в раздел кода, изменение которого не допускается при использовании операции "Изменить и продолжить" языка Visual C\#.  
  
 Операция "Изменить и продолжить" в [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)] позволяет остановить выполнение программы в режиме приостановки выполнения, внести изменения в исполняемый код, а затем возобновить выполнение программы с учетом внесенных изменений.  
  
 Изменения в объявляющем коде, меняющие общедоступную \(public\) структуру класса, в общем случае запрещены. Кроме того, не разрешены некоторые виды изменений в теле метода или свойства, а также в объявлениях со спецификатором доступа private в пределах класса. Операция "Изменить и продолжить" по возможности помечает запрещенный к изменению код светло\-серым и отображает сообщение об ошибке.  
  
 Дополнительные сведения об изменениях, поддерживаемых операцией "Изменить и продолжить" для [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)], см. в разделе [Поддерживаемые изменения кода \(C\#\)](../Topic/Supported%20Code%20Changes%20\(C%23\).md). Если требуются дополнительные сведения о конкретной ошибке или предупреждении, можно поискать ответ или разместить вопрос на [форуме по IDE Visual C\#](http://go.microsoft.com/fwlink/?LinkId=214693) на веб\-сайте MSDN.  
  
### Исправление ошибки  
  
1.  Выберите команду **Отменить** в меню **Отладка** для отмены изменений.  
  
     \-или\-  
  
2.  Остановите сеанс отладки, внесите изменения и начните новый сеанс отладки.  
  
## См. также  
 [Режим "Изменить и продолжить" \(Visual C\#\)](../Topic/Edit%20and%20Continue%20\(Visual%20C%23\).md)