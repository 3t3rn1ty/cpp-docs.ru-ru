---
title: "/Zc:auto (выведение типа переменной) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:auto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc - параметры компилятора (C++)"
  - "выведение типа переменной (C++)"
  - "Zc - параметры компилятора (C++)"
  - "-Zc - параметры компилятора (C++)"
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Zc:auto (выведение типа переменной)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр компилятора **\/Zc:auto\[\-\]** указывает компилятору, как следует использовать [ключевое слово auto](../../cpp/auto-keyword.md) для объявления переменных.  Если указан параметр по умолчанию \(**\/Zc:auto**\), компилятор выводит тип объявленной переменной из выражения инициализации.  Если указан оператор  **\/Zc:auto\-**, компилятор выделяет переменную для автоматического класса хранения.  
  
## Синтаксис  
  
```  
/Zc:auto[-]  
```  
  
## Заметки  
 Стандарт языка C\+\+ определяет первоначальное и измененное значение ключевого слова `auto`.  До версии [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] ключевое слово объявляло переменную в автоматическом классе хранения, то есть переменную с локальным временем существования.  Начиная с версии [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] ключевое слово выводит тип переменной из выражения инициализации объявления. Параметр компилятора **\/Zc:auto\[\-\]** используется для указания компилятору на необходимость использования первоначального или измененного значения ключевого слова `auto`.  
  
 Компилятор выдает соответствующее диагностическое сообщение, если применение ключевого слова `auto` противоречит текущему параметру компилятора.  Для получения дополнительной информации см. [Ключевое слово auto](../../cpp/auto-keyword.md).  Дополнительные сведения о вопросах соответствия, связанных с Visual C\+\+, см. в разделе [Нестандартное поведение](../Topic/Nonstandard%20Behavior.md).  
  
### Установка параметра компилятора в Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Щелкните узел **Свойства конфигурации**.  
  
3.  Щелкните узел **C\/C\+\+**.  
  
4.  Выберите узел **Командная строка**.  
  
5.  Добавьте **\/Zc:auto** или **\/Zc:auto\-** в область **Дополнительные параметры**.  
  
## См. также  
 [\/Zc \(соответствие\)](../../build/reference/zc-conformance.md)   
 [Ключевое слово auto](../../cpp/auto-keyword.md)