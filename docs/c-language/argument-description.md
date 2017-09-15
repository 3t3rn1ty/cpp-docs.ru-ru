---
title: "Описание аргумента | Документация Майкрософт"
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
- envp argument
- main function, syntax
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
caps.latest.revision: 10
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
ms.openlocfilehash: 588d052380286498181b1062f616618408e5fe99
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="argument-description"></a>Описание аргумента
Параметр `argc` в функциях **main** и **wmain** выражается целым числом и обозначает количество аргументов, переданных в программу из командной строки. Поскольку имя программы считается аргументом, значение `argc` по крайней мере равно единице.  
  
## <a name="remarks"></a>Примечания  
 Параметр `argv` является массивом указателей на строки, завершающиеся значением NULL, который представляет аргументы программы. Каждый элемент массива указывает на строковое представление аргумента, переданного в **main** (или **wmain**). (Дополнительные сведения о массивах см. в разделе [Объявления массивов](../c-language/array-declarations.md).) Параметр `argv` можно объявить как массив указателей на тип `char` (`char *argv[]`) или как указатель на указатели на тип `char` (`char **argv`). Параметр `argv` в **wmain** можно объявить как массив указателей на тип `wchar_t` (`wchar_t *argv[]`) или как указатель на указатели на тип `wchar_t` (`wchar_t **argv`).  
  
 По соглашению параметр `argv`**[0]** содержит команду, которая использовалась для вызова программы.  Однако процесс можно инициализировать с помощью [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425), а если указаны и первый, и второй аргументы (`lpApplicationName` и `lpCommandLine`), то `argv`**[0]** не будет содержать имени исполняемого файла. Чтобы гарантированно получить имя исполняемого файла, используйте [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197).  
  
 Последний указатель (`argv[argc]`) имеет значение **NULL**. (Альтернативный метод получения сведений о переменной среды см. в разделе [getenv](../c-runtime-library/reference/getenv-wgetenv.md) *Справочника по библиотеке времени выполнения*.)  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Параметр `envp` является указателем на массив строк, завершающихся значением NULL, которые представляют значения, заданные в переменных среды пользователя. Параметр `envp` можно объявить как массив указателей на тип `char` (`char *envp[]`) или как указатель на указатели на тип `char` (`char **envp`). Параметр `envp` в функции **wmain** можно объявить как массив указателей на `wchar_t` (`wchar_t *envp[]`) или как указатель на указатели на `wchar_t` (`wchar_t **envp`). Конец массива определяется указателем **NULL** \*. Обратите внимание, что передаваемый в **main** или **wmain** блок окружения является "замороженной" копией текущего окружения. Если окружение будет позднее изменена путем вызова **_putenv** или `_wputenv`, изменится только текущее окружение (которое возвращают `getenv`/`_wgetenv` и переменные `_environ` или `_wenviron`); но не блок, на который указывает `envp`. Параметр `envp` совместим с ANSI в C, но не в C++.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main и выполнение программ](../c-language/main-function-and-program-execution.md)