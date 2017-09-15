---
title: "Исключения. Использование макросов MFC и исключений C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "catch - блоки, явное удаление кода в"
  - "catch - блоки, смешанный"
  - "обработка исключений, MFC - библиотека"
  - "обработка исключений, смешанный язык"
  - "объекты исключения"
  - "объекты исключения, удаление"
  - "исключения, макросы MFC или ключевые слова C++"
  - "повреждение кучи"
  - "утечки памяти, объект исключения не удален"
  - "вложенные блоки catch"
  - "вложенные блоки try"
  - "обработка исключений try-catch, смешение макросов MFC и ключевых слов C++"
  - "обработка исключений try-catch, вложенные блоки try"
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Исключения. Использование макросов MFC и исключений C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье рассматриваются вопросы написания кода, использующего и макросы обработки исключений MFC и ключевые слова обработки исключений C\+\+.  
  
 Этот раздел охватывает следующее:  
  
-   [Смешивание ключевые слова и макросы исключения](#_core_mixing_exception_keywords_and_macros)  
  
-   [Блоки catch блоков try внутренние](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a> Смешивание ключевые слова и макросы исключения  
 Ключевые слова можно макросов MFC исключения набора исключений C\+\+ в одной программе.  Однако нельзя макросов MFC набора с ключевыми словами исключения C\+\+ в одном блоке, поскольку макросы удаляют объекты исключений автоматически, если они находятся вне области, тогда как код с помощью ключевых слов обработки исключений не требуется.  Дополнительные сведения см. в статье [Исключения: Улавливающ и удаление исключения](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Основное различие между макросами и ключевыми словами, макросы «автоматически» удаление перехваченное исключение при возникновении исключения выходит за пределы области действия.  Код с помощью ключевого слова не выполняется; перехваченные исключения в блоке catch должна быть явно удалена.  Ключевые слова смешивание макросы исключение C\+\+ могут привести к утечке памяти, когда объект исключения не удален, или повреждения кучи, когда исключение удаляется дважды.  
  
 В следующем коде, например, что указатель исключения:  
  
 [!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/CPP/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]  
  
 Проблема возникает, поскольку `e` удаляется при выполнении передает «из» внутреннего блока **CATCH**.  Использование макроса `THROW_LAST` вместо выписки **THROW** приведет к «» внешний блок **CATCH** получить допустимый указатель.  
  
 [!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/CPP/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a> Блоки catch блоков try внутренние  
 Невозможно повторно ход текущее исключение из блока **try** внутри блока **CATCH**.  Следующий пример является недопустимым:  
  
 [!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/CPP/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]  
  
 Дополнительные сведения см. в разделе [Исключения: Просмотр содержимого исключения](../mfc/exceptions-examining-exception-contents.md).  
  
## См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)