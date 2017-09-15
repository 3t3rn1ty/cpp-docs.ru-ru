---
title: "Включение имен файлов в кавычках | Документация Майкрософт"
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
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
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
ms.openlocfilehash: 70b5e68fc8a3c0c23b291220e4faf387e9aa11c2
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="including-quoted-filenames"></a>Включение имен файлов в кавычках
**ANSI 3.8.2** Поддержка заключенных в кавычки имен для включаемых файлов исходного кода  
  
 Если указана полная и неоднозначная спецификация пути для включаемого файла между двумя наборами двойных кавычек (" "), препроцессор ищет только спецификацию пути и игнорирует стандартные каталоги.  
  
 Для включаемых файлов, заданных в виде [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec", поиск по каталогам начинается с каталога родительского файла и продолжается по каталогам всех прародительских файлов. Таким образом, поиск начинается относительно каталога, который содержит обрабатываемый в настоящее время файл исходного кода. Если отсутствует файл "прародителя" и файл не найден, поиск продолжается, как если бы имя файла было включено в угловые скобки.  
  
## <a name="see-also"></a>См. также  
 [Директивы предварительной обработки](../c-language/preprocessing-directives.md)