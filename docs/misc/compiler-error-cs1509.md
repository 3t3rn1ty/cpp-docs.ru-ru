---
title: "Ошибка компилятора CS1509 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1509"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1509"
ms.assetid: 51a475c3-f085-49cb-89b0-c6582b68653f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS1509
Указанный файл "файл" не является сборкой. Используйте параметр "\/addmodule"  
  
 Выходной файл \(выходной файл 1\), полученный при компиляции с использованием [\/target:module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md) \(без манифеста сборки\), был указан для параметра [\/reference](../Topic/-reference%20\(C%23%20Compiler%20Options\).md). Таким образом вместо добавления этой сборки в сборку для текущей программы будут добавлены сведения метаданных из выходного файла 1.