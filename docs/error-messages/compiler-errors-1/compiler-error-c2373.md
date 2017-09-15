---
title: "Ошибка компилятора C2373 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2373
dev_langs:
- C++
helpviewer_keywords:
- C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 3d1bb48d4ee1fe4977ae5a3352bc77786ab3f538
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2373"></a>Ошибка компилятора C2373
"идентификатор": переопределение; различные модификаторы типа  
  
 Идентификатор уже объявлен с другим модификатором типа.  
  
 Следующий пример приводит к возникновению ошибки C2373:  
  
```  
// C2373.h  
void __clrcall func( void );  
const int i = 20;  
```  
  
 Затем:  
  
```  
// C2373.cpp  
// compile with: /c  
#include "C2373.h"  
extern void __cdecl func( void );   // C2373  
extern void __clrcall func( void );   // OK  
  
extern int i;   // C2373  
extern const int i;   // OK  
```