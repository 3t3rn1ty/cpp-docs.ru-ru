---
title: "Предупреждение компилятора (уровень&#160;1) C4935 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4935"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4935"
ms.assetid: a36c56d3-571a-44dd-bb0f-bcc6b020e134
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;1) C4935
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

спецификатор уровня доступа сборки изменен из "уровень доступа"  
  
 Был изменена область видимости типа на уровне сборки. Компилятор использует последний обнаруженный спецификатор. Например, область видимости опережающего объявления на уровне сборки может отличаться от области видимости определения класса на уровне сборки.  
  
 Предупреждение C4935 возникает только при использовании **\/clr:oldSyntax**.  
  
 Следующий пример приводит к возникновению предупреждения C4935:  
  
```  
// C4935.cpp // compile with: /clr:oldSyntax /W1 /c public __gc public class X {   // C4935 int i; };  
```