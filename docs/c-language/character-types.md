---
title: "Символьные типы | Документация Майкрософт"
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
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
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
ms.openlocfilehash: f0f8639e90787ddcc90b7a302f226d305f29dce1
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="character-types"></a>Символьные типы
Целочисленная символьная константа, в начале которой не указана буква **L**, имеет тип `int`. Значением целой символьной константы, содержащей один символ, является численное значение символа, интерпретированное как целое число. Например, численное значение символа `a` равно 97 в десятичном представлении и 61 в шестнадцатеричном представлении.  
  
 Синтаксически "расширенная символьная константа" представляет собой символьную константу с префиксом в виде буквы **L**. Расширенная символьная константа имеет тип `wchar_t` — целочисленный тип, определенный в файле заголовка STDDEF.H. Пример:  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Расширенные символьные константы имеют ширину 16 бит и указывают члены расширенной кодировки выполнения. Они обеспечивают представление символов в алфавитах, слишком больших для представления типом `char`. Дополнительные сведения о расширенных символах см. в статье [Многобайтовые и расширенные символы](../c-language/multibyte-and-wide-characters.md).  
  
## <a name="see-also"></a>См. также  
 [Константы символов в C](../c-language/c-character-constants.md)