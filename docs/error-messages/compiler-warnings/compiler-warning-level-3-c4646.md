---
title: "Ошибка компилятора предупреждение (уровень 3) C4646 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4646
dev_langs:
- C++
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
caps.latest.revision: 7
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
ms.openlocfilehash: 9fe7c1ca87dd80133e4073f41ad434dd24052db5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4646"></a>Предупреждение компилятора (уровень 3) C4646
функция, объявленная с атрибутом __declspec(noreturn) имеет тип, отличный от void  
  
 Функция, помеченная [noreturn](../../cpp/noreturn.md) `__declspec` должен иметь модификатор [void](../../cpp/void-cpp.md) тип возвращаемого значения.  
  
 В следующем примере возникает ошибка C4646.  
  
```  
// C4646.cpp  
// compile with: /W3 /WX  
int __declspec(noreturn) TestFunction()  
{   // C4646  make return type void  
}  
```