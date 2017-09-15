---
title: "Оценка лексем | Документация Майкрософт"
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
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
caps.latest.revision: 8
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
ms.openlocfilehash: 72ed41d37222046f6dfa594aedaa30a0bb38756b
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="evaluation-of-tokens"></a>Оценка токенов
Когда компилятор интерпретирует токены, он включает в один токен максимально возможное количество символов, а затем переходит к следующему. Поэтому если токены не разделены пробельными символами, они могут интерпретироваться не так, как ожидается. Рассмотрим следующее выражение:  
  
```  
i+++j  
```  
  
 В этом примере компилятор сначала извлекает максимально возможный оператор (`++`) из последовательности знаков "плюс", а затем обрабатывает последний знак "плюс" как оператор сложения (`+`). Таким образом, выражение интерпретируется как `(i++) + (j)`, а не как `(i) + (++j)`. Для того чтобы предотвратить неоднозначность и гарантировать правильное вычисление выражений, в подобных случаях рекомендуется использовать пробелы и скобки.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Компилятор C обрабатывает символ CTRL+Z как индикатор конца файла. Весь текст, расположенный после символа CTRL+Z, игнорируется.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Токены C](../c-language/c-tokens.md)