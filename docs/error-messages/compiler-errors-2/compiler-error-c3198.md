---
title: "Ошибка компилятора C3198 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3198"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3198"
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3198
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимое использование директив pragma с плавающей запятой: директива pragma fenv\_access работает только в режиме повышенной точности  
  
 Директива pragma [fenv\_access](../../preprocessor/fenv-access.md) использована в то время, как настройки параметра [\/fp](../../build/reference/fp-specify-floating-point-behavior.md) отличаются от **\/fp:precise**.  
  
 Следующий пример приводит к возникновению ошибки C3198:  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```