---
title: "Утверждение и сообщения об ошибках, предоставленные пользователем (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "#error%2C assert%2C static_assert [C++]"
  - "предоставленные пользователем сообщения [C++], время компиляции"
  - "предоставленные пользователем сообщения [C++], время препроцессора"
  - "предоставленные пользователем сообщения [C++], время выполнения"
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Утверждение и сообщения об ошибках, предоставленные пользователем (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В языке C\+\+ поддерживаются три механизма обработки ошибок, помогающие отлаживать приложения: [директива \#error](../preprocessor/hash-error-directive-c-cpp.md), ключевое слово [static\_assert](../cpp/static-assert.md) и макрос [Макрос assert, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md).  Все три механизма создают сообщения об ошибках, а два их них также проверяют утверждения программного обеспечения.  Программное утверждение определяет условие, которое должно выполняться на определенном этапе работы программы.  Если утверждение времени компиляции ложно, компилятор создает диагностическое сообщение и ошибку компиляции.  Если утверждение времени выполнения ложно, операционная система выводит диагностическое сообщение и закрывает приложение.  
  
## Заметки  
 Жизненный цикл приложения состоит из этапа предварительной обработки, этапа компиляции и этапа времени выполнения.  Каждый механизм обработки ошибок обращается к отладочной информации, доступной в ходе одного из этих этапов.  Для эффективной отладки выберите механизм, обеспечивающий требуемую информацию об этом этапе.  
  
-   [Директива \#error](../preprocessor/hash-error-directive-c-cpp.md) действует во время предварительной обработки.  Она безусловно выводит определенное пользователем сообщение и вызывает сбой компиляции с ошибкой.  Сообщение может содержать текст, управляемый директивами препроцессора, но никакие результирующие выражения не вычисляются.  
  
-   Объявление [static\_assert](../cpp/static-assert.md) действует во время компиляции.  Оно проверяет утверждения программного обеспечения, которые определяются заданным пользователем целочисленным выражением, допускающим преобразование в логическое значение.  Если выражение равно нулю \(ложно\), компилятор выдает определенное пользователем сообщение и компиляция завершается сбоем с ошибкой.  
  
     Объявления `static_assert` особенно полезны для отладки шаблонов, так как аргументы шаблона можно включать в определенное пользователем выражение.  
  
-   Макрос [Макрос assert, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) действует во время выполнения.  Он вычисляет определенное пользователем выражение, и если результат равен нулю, система выводит диагностическое сообщение и закрывает приложение.  Многие другие макросы, например [\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) и `_ASSERTE`, похожи на этот макрос, но выдают другие диагностические сообщения, определяемые системой или пользователем.  
  
## См. также  
 [Директива \#error](../preprocessor/hash-error-directive-c-cpp.md)   
 [Макрос assert, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Макросы \_ASSERT, \_ASSERTE, \_ASSERT\_EXPR](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)   
 [static\_assert](../cpp/static-assert.md)   
 [Макрос \_STATIC\_ASSERT](../c-runtime-library/reference/static-assert-macro.md)   
 [Шаблоны](../Topic/Templates%20\(C++\).md)