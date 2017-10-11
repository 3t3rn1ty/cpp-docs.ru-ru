---
title: "Ошибка компилятора C2348 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2348
dev_langs:
- C++
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2be3e9c8d83443355c3090dd3083f800ae55d76d
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2348"></a>Ошибка компилятора C2348
«имя_типа»: не является агрегированным в стиле C, невозможно экспортировать во внедренный IDL  
  
 Чтобы поместить `struct` в IDL-файл с [экспорта](../../windows/export.md) атрибут `struct` должен содержать только данные.  
  
 Следующий пример приводит к возникновению ошибки C2348:  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```
