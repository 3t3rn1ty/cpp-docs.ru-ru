---
title: "Побочные эффекты | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation, side effects
- side effects in expression evaluation
ms.assetid: d9b3004a-830e-43a0-bea5-8989d501d670
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: dbd2046e8f714196d2caa85111d01e25a2a7063e
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="side-effects"></a>Побочные эффекты
Порядок вычисления выражений определяется конкретной реализацией, за исключением случаев, когда язык гарантирует определенный порядок вычислений (как описано в статье [Приоритет и порядок оценки](../c-language/precedence-and-order-of-evaluation.md)). Например, в следующих вызовах функций возникают побочные эффекты:  
  
```  
add( i + 1, i = j + 2 );  
myproc( getc(), getc() );  
```  
  
 Аргументы вызова функции могут вычисляться в любом порядке. Выражение `i + 1` может вычисляться до выражения `i = j + 2` или выражение `i = j + 2` может вычисляться до выражения `i + 1`. В каждом случае результат будет различным. Аналогично, невозможно гарантировать, какие символы фактически будут переданы в `myproc`. Поскольку унарные операции инкремента и декремента связаны с присваиваниями, такие операции могут вызывать побочные эффекты, как показано в следующем примере:  
  
```  
x[i] = i++;  
```  
  
 В этом примере значение изменяемой переменной `x` непредсказуемо. Значение индекса может быть как новым, так и старым значением переменной `i`. Результат может отличаться в различных компиляторах или при разных уровнях оптимизации.  
  
 Поскольку язык C не определяет порядок вычисления побочных эффектов, оба приведенных выше метода вычисления правильны и оба могут быть реализованы. Чтобы обеспечить переносимость и понятность кода, не используйте операторы, зависящие от конкретного порядка вычисления побочных эффектов.  
  
## <a name="see-also"></a>См. также  
 [Вычисление выражений](../c-language/expression-evaluation-c.md)