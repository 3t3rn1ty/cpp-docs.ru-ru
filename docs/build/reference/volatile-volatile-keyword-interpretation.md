---
title: "/volatile (интерпретация ключевого слова volatile) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/volatile:iso"
  - "/volatile:ms"
  - "/volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Параметр компилятора "/volatile""
  - "Параметр компилятора "/volatile" [C++]"
  - "Параметр компилятора "volatile""
  - "Параметр компилятора "-volatile""
  - "Параметр компилятора "volatile" [C++]"
  - "Параметр компилятора "-volatile" [C++]"
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# /volatile (интерпретация ключевого слова volatile)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает способ интерпретации ключевого слова [volatile](../../cpp/volatile-cpp.md).  
  
## Синтаксис  
  
```  
/volatile:{iso|ms}  
```  
  
## Аргументы  
 **\/volatile:iso**  
 Выделяет строгую семантику `volatile`, как определено стандартным языком С\+\+ для ISO\-образов.  Семантика получения и освобождения не гарантируется при переменном обращении.  Если компилятор нацелен на ARM, это интерпретация `volatile` по умолчанию.  
  
 **\/volatile:ms**  
 Выделяет расширенную семантику `volatile` Microsoft, которая добавляет гарантии упорядочения памяти за пределами стандартного языка С\+\+ для ISO\-образов.  Семантика получения и освобождения гарантируется при переменном обращении.  Однако этот параметр также заставляет компилятор генерировать барьеры памяти оборудования, которые могут добавлять значительную нагрузку на ARM и другие архитектуры со слабым упорядочиванием памяти.  Если компилятор нацелен на какую\-либо платформу, кроме ARM, это интерпретация `volatile` по умолчанию.  
  
## Заметки  
 Настоятельно рекомендуется использовать **\/volatile:iso** вместе с явными примитивами синхронизации и встроенными компилятора при работе с памятью, используется отладкой потоков.  Для получения дополнительной информации см. [volatile](../../cpp/volatile-cpp.md).  
  
 Если перенести существующий код или изменить этот параметр посередине проекта, возможно, имеет смысл включить предупреждение [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md), чтобы определить расположения кода, затронутые отличиями в семантике.  
  
 Значение `#pragma` эквивалентно элементу управления этот параметр.  
  
### Задание параметра компилятора \/volatile в Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Для получения дополнительной информации см. [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  В поле **Дополнительные параметры** добавьте `/volatile: ISO` или `/volatile: отсутствуют`.  
  
## См. также  
 [volatile](../../cpp/volatile-cpp.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)