---
title: "/arch (x86) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# /arch (x86)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает архитектуру для создания кода на платформе x86.  См. также [\/arch \(x64\)](../../build/reference/arch-x64.md) и [\/arch \(ARM\)](../../build/reference/arch-arm.md).  
  
## Синтаксис  
  
```  
/arch:[IA32|SSE|SSE2|AVX|AVX2]  
```  
  
## Аргументы  
 **\/arch:IA32**  
 Указывает на то, что расширенные инструкции не используются. Также указывает на использование инструкций x87 для вычислений с плавающей запятой.  
  
 **\/arch:SSE**  
 Позволяет использовать инструкции SSE.  
  
 **\/arch:SSE2**  
 Позволяет использовать инструкции SSE2.  Это инструкция по умолчанию на платформах x86, если параметр **\/arch** не указан.  
  
 **\/arch:AVX**  
 Позволяет использовать инструкции Intel AVX.  
  
 **\/arch:AVX2**  
 Позволяет использовать инструкции Intel AVX 2.  
  
## Заметки  
 Наборы инструкций SSE и SSE2 имеются в различных процессорах Intel и AMD.  Инструкции AVX существуют в процессорах Intel Sandy Bridge и процессорах AMD Bulldozer.  Инструкции AVX2 поддерживаются процессорами Intel Haswell и Broadwell, а также процессорами на основе AMD Excavator.  
  
 Макросы `_M_IX86_FP`, `__AVX__` и `__AVX2__` указывают, какой параметр компиляции **\/arch** использовался \(если использовался\).  Подробнее: [Предустановленный макрос](../../preprocessor/predefined-macros.md).  Параметр **\/arch:AVX2** и макрос `__AVX2__` появились в Visual Studio 2013 с обновлением 2 версии 12.0.34567.1.  
  
 Если указан параметр **\/arch**, то оптимизатор выбирает, где и как применять наборы инструкций SSE и SSE2.  Наборы инструкций SSE и SSE2 будут использоваться при некоторых скалярных вычислениях с плавающей запятой, если будет обнаружено, что регистры и инструкции SSE или SSE2 дают выигрыш во времени по сравнению со стеком регистров с плавающей запятой x87.  В результате код будет использовать для вычислений с плавающей запятой как инструкции x87, так и SSE\/SSE2.  Кроме того, с параметром **\/arch:SSE2** набор инструкций SSE2 может использоваться для операций с целыми 64\-разрядными числами.  
  
 В дополнение к наборам инструкций SSE и SSE2 компилятор также использует другие инструкции, имеющиеся в редакциях процессоров, поддерживающих SSE и SSE2.  Примером может служить инструкция CMOV, которая впервые появилась в редакции Pentium Pro процессоров Intel.  
  
 Компилятор x86 создает код, который по умолчанию использует инструкции SSE2. Поэтому чтобы отключить создание инструкций SSE и SSE2 для процессоров x86, необходимо указать параметр **\/arch:IA32**.  
  
 **\/arch** влияет только на создание кода для собственных функций.  При компиляции с помощью [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) параметр **\/arch** не оказывает влияния на создание кода для управляемых функций.  
  
 Нельзя использовать **\/arch** и [\/QIfist](../../build/reference/qifist-suppress-ftol.md) в одной единице компиляции.  В частности, если вы не используете `_controlfp` для изменения контрольного слова FP, то код запуска времени выполнения установит 53 бита для поля управления точностью контрольного слова FPU x87.  Поэтому каждая операция с типами float и double в выражении выполняется с 53\-разрядной мантиссой и 15\-разрядной экспонентой.  Тем не менее, все операции SSE одиночной точности используют 24\-разрядную значащую часть и 8\-разрядную экспоненту, а операции SSE2 двойной точности используют 53\-разрядную значимую часть и 11\-разрядную экспоненту.  Подробнее: [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md).  Подобные отличия возможны в пределах одного дерева выражения, но не в том случае, когда после каждой части выражения стоит пользовательское присваивание.  Рассмотрим следующий пример.  
  
```c  
  
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.  
```  
  
 Рассмотрим другую ситуацию.  
  
```c  
  
t = f1 * f2;   // Do f1 * f2, round to the type of t.  
r = t + d;     // This should produce the same overall result   
               // whether x87 stack is used or SSE/SSE2 is used.  
```  
  
### Установка параметра компилятора для AVX, AVX2, IA32, SSE или SSE2 в Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Подробнее: [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Выберите папку **Свойства конфигурации**, а затем папку **C\/C\+\+**.  
  
3.  Выберете страницу свойств **Создание кода**.  
  
4.  Измените свойство **Включить расширенный набор инструкций**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## См. также  
 [\/arch \(минимальная архитектура ЦП\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)