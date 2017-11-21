---
title: "Ошибка компилятора C3168 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3168
dev_langs: C++
helpviewer_keywords: C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 980341a7871d314e3173449234fbb597a5b55d63
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3168"></a>Ошибка компилятора C3168
«Тип»: недопустимый базовый тип для перечисления  
  
Базовый тип, указанный для `enum` указан недопустимый тип. Базовый тип должен быть целым типом C++ или соответствующий тип CLR.  
  
Следующий пример приводит к возникновению ошибки C3168:  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
