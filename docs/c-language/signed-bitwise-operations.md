---
title: "Битовые операции со знаком | Документы Майкрософт"
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
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e3e4eeb1c71752c7e682bc500afacb730162abca
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="signed-bitwise-operations"></a>Битовые операции со знаком
**ANSI 3.3** Результаты выполнения побитовых операций над знаковыми целочисленными значениями  
  
 Побитовые операции над знаковыми целочисленными значениями работают так же, как и над беззнаковыми. Например, значение `-16 & 99` можно представить в двоичном виде следующим образом:  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Результат выполнения побитовой операции И будет равен 96.  
  
## <a name="see-also"></a>См. также  
 [Целые числа](../c-language/integers.md)