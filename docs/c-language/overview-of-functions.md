---
title: "Общие сведения о функциях | Документация Майкрософт"
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
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
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
ms.openlocfilehash: 16612a32a0e5cb2294f4b74f46c14c206c1cbcbc
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="overview-of-functions"></a>Общие сведения о функциях
Функции должны иметь определение и объявление, хотя определение может служить объявлением, если объявление находится до вызова функции. Определение функции включает тело функции — код, который выполняется при вызове функции.  
  
 Объявление функции указывает имя, возвращаемый тип и атрибуты функции, определенной в любом другом месте программы. Объявление функции должно предшествовать вызову функции. Именно поэтому файлы заголовков, содержащие объявления для функций времени выполнения, включаются в код перед вызовом функции времени выполнения. Если объявление содержит сведения о типах и количестве параметров, оно является прототипом. Дополнительные сведения см. в статье [Прототипы функций](../c-language/function-prototypes.md).  
  
 Компилятор использует прототип для сравнения типов аргументов в последующих вызовах функции с параметрами функции и для преобразования типов аргументов в типы параметров, если это необходимо.  
  
 В вызове функции управление выполнением передается из вызывающей функции в вызываемую функцию. Аргументы, если таковые имеются, передаются по значению в вызываемую функцию. При выполнение оператора `return` в вызываемой функции управление и, возможно, значение возвращаются в вызывающую функцию.  
  
## <a name="see-also"></a>См. также  
 [Функции](../c-language/functions-c.md)