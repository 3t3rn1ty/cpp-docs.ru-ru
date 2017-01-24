---
title: "Ошибка компилятора C2707 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2707"
ms.assetid: 3deaf45c-74da-4c9d-acc6-b82412720b74
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": неправильный контекст для подставляемой функции  
  
 Структурные встроенные макроопределения обработки исключений недопустимы в определенных контекстах:  
  
-   `_exception_code()` вне фильтра исключений или блок `__except`  
  
-   `_exception_info()` вне фильтра исключений  
  
-   `_abnormal_termination()` вне блока `__finally`  
  
 Чтобы исправить ошибку, убедитесь, что встроенные макроопределения обработки исключений помещены в соответствующий контекст.  
  
## Пример  
 В следующем примере показано возникновение ошибки C2707.  
  
```  
// C2707.cpp  
#include <windows.h>  
#include <stdio.h>  
  
LONG MyFilter(LONG excode)   
{  
    return (excode == EXCEPTION_ACCESS_VIOLATION ?  
        EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);   // OK  
}  
  
LONG func(void)   
{  
    int x, y;  
    return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ?  // C2707  
             EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
  
    __try   
    {  
        y = 0;  
        x = 4 / y;  
        return 0;  
     }  
  
    __except(MyFilter(GetExceptionCode()))   
    {  
        return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ? // ok  
               EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
    }  
}  
  
int main()   
{  
    __try   
    {  
        func();  
    } __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf_s("Caught exception\n");  
    }  
}  
```