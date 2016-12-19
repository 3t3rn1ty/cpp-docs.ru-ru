---
title: "Ошибка компилятора C3047 | Microsoft Docs"
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
  - "C3047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3047"
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структурированному блоку в области OpenMP "sections" должна предшествовать директива "\#pragma omp section"  
  
 Любой код в блоке кода, представленного директивой [sections](../../parallel/openmp/reference/sections-openmp.md), должен быть в блоке кода, представленном директивой `section`.  
  
 Следующий пример приводит к возникновению ошибки C3047:  
  
```  
// C3047.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { #pragma omp section { ++n3; } ++n2;   // C3047 not enclosed in #pragma omp section } } }  
```