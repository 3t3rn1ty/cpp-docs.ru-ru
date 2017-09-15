---
title: "Неустранимая ошибка C1067 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1067"
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка C1067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

предел компилятора: превышен предельный размер 64K для записи типа  
  
 Эта ошибка возникает, если длина внутреннего имени символа превышает 247 символов.  Чтобы устранить ошибку, сократите имя символа.  
  
 При создании сведений по отладке, компилятор выдает записи типа, чтобы определить типы, встречающиеся в исходном коде.  Например, записи типа могут включать простые структуры и списки аргументов, относящихся к функциям.  Некоторые записи типов могут представлять собой длинные списки.  
  
 Для записей типа установлено ограничение по размеру — 64 КБ.  Если размер записи превышает установленный предел в 64 КБ, возникает ошибка.  
  
 Ошибка C1067 также может быть вызвана большим количеством символов с длинными именами или же большим количеством членов в классе, структуре или объединении.