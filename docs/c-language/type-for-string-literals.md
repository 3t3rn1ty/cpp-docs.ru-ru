---
title: "Тип для строковых литералов | Документация Майкрософт"
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
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
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
ms.openlocfilehash: 8e8d285bf85c711bd6adcbdb45c6384ea2309dc0
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="type-for-string-literals"></a>Тип для строковых литералов
Строковые литералы имеют тип массива `char` (т. е., **char[ ]**). (Строки расширенных символов имеют тип массива `wchar_t` (т. е., **wchar_t []**).) Это означает, что строка является массивом с элементами типа `char`. Число элементов в массиве равно числу символов в строке плюс один дополнительный элемент для завершающего символа null.  
  
## <a name="see-also"></a>См. также  
 [Строковые литералы в C](../c-language/c-string-literals.md)