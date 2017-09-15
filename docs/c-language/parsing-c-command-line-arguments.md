---
title: "Анализ аргументов командной строки C | Документация Майкрософт"
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
- quotation marks, command-line arguments
- double quotation marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
caps.latest.revision: 8
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
ms.openlocfilehash: 66f9ab28bfec3fe0cfd9d29d60a0ee7ac283591a
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="parsing-c-command-line-arguments"></a>Анализ аргументов командной строки C
**Блок, относящийся только к системам Майкрософт**  
  
 В коде запуска Microsoft C используются следующие правила при обработке аргументов, вводимых в командной строке операционной системы.  
  
-   Аргументы разделяются пробелами (пробел или табуляция).  
  
-   Строка, заключенная в двойные прямые кавычки, обрабатывается как один аргумент, независимо от пробельных символов, которые могут в ней присутствовать. Строку в кавычках можно встроить в аргумент. Обратите внимание, что символ каретки (**^**) не воспринимается как escape-символ или разделитель.  
  
-   Символ двойной кавычки после обратной косой черты (**\\"**) обрабатывается как литеральный символ двойной кавычки (**"**).  
  
-   Символы обратной косой черты обрабатываются буквально, если только им не предшествует двойная кавычка.  
  
-   Если двойная кавычка стоит после четного числа символов обратной косой черты, в массив `argv` помещается по одному символу обратной косой черты (**\\**) для каждой пары символов обратной косой черты (**\\\\**), а двойная кавычка (**"**) обрабатывается как разделитель строк.  
  
-   Если двойная кавычка стоит после нечетного числа символов обратной косой черты, в массив `argv` помещается по одному символу обратной косой черты (**\\**) для каждой пары символов обратной косой черты (**\\\\**), а символ двойной кавычки с оставшимся символом обратной косой черты интерпретируется как escape-последовательность, в результате чего в массив `argv` помещается литеральный символ двойной кавычки (**"**).  
  
 В следующем списке, иллюстрирующем указанные выше правила, показаны результаты, передаваемые в массив `argv` для нескольких примеров аргументов командной строки. Выходные данные, представленный во втором, третьем и четвертом столбцах, получены из программы ARGS.C, приведенной после списка.  
  
|Данные в командной строке|argv[1]|argv[2]|argv[3]|  
|-------------------------|---------------|---------------|---------------|  
|`"a b c" d e`|`a b c`|`d`|`e`|  
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|  
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```  
// Parsing_C_Commandline_args.c  
// ARGS.C illustrates the following variables used for accessing  
// command-line arguments and environment variables:  
// argc  argv  envp  
//  
  
#include <stdio.h>  
  
int main( int argc, // Number of strings in array argv  
 char *argv[],      // Array of command-line argument strings  
 char **envp )      // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    printf_s( "\nCommand-line arguments:\n" );  
    for( count = 0; count < argc; count++ )  
        printf_s( "  argv[%d]   %s\n", count, argv[count] );  
  
    // Display each environment variable.  
    printf_s( "\nEnvironment variables:\n" );  
    while( *envp != NULL )  
        printf_s( "  %s\n", *(envp++) );  
  
    return;  
}  
```  
  
## <a name="comments"></a>Комментарии  
 Ниже приведен один пример данных, выводимых этой программой:  
  
```  
Command-line arguments:  
  argv[0]   C:\MSC\TEST.EXE  
  
Environment variables:  
  COMSPEC=C:\NT\SYSTEM32\CMD.EXE  
  
  PATH=c:\nt;c:\binb;c:\binr;c:\nt\system32;c:\word;c:\help;c:\msc;c:\;  
  PROMPT=[$p]   
  TEMP=c:\tmp  
  TMP=c:\tmp  
  EDITORS=c:\binr  
  WINDIR=c:\nt        
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main и выполнение программ](../c-language/main-function-and-program-execution.md)