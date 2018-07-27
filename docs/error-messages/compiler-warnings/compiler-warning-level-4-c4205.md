---
title: Предупреждение (уровень 4) C4205 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4205
dev_langs:
- C++
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc8c811fd8d67964bdef8149aea09d83e4649b99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292770"
---
# <a name="compiler-warning-level-4-c4205"></a>Предупреждение компилятора (уровень 4) C4205
использовано нестандартное расширение: объявление статической функции в области видимости функции  
  
 С расширениями Майкрософт (/Ze) **статических** функции могут быть объявлены внутри другой функции. Функция имеет глобальную область.  
  
## <a name="example"></a>Пример  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 Подобная инициализация не допускается в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).