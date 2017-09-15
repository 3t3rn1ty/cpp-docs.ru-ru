---
title: "hash_multimap::swap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap - член [STL/CLR]"
ms.assetid: 4baa60c2-865a-4e17-acd5-01b7c3c5cd44
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_multimap::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Меняет местами содержимое двух контейнеров.  
  
## Синтаксис  
  
```  
void swap(hash_multimap<Key, Mapped>% right);  
```  
  
#### Параметры  
 правый  
 Контейнер для обмена содержимым.  
  
## Заметки  
 Меняет местами функции\-члена из последовательности между `this` и `right`.  Это происходит при расчете времени и не создает исключений.  Он используется как быстрый способ обмена содержимое 2 контейнеров.  
  
## Пример  
  
```  
// cliext_hash_multimap_swap.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Myhash_multimap c2;   
    c2.insert(Myhash_multimap::make_value(L'd', 4));   
    c2.insert(Myhash_multimap::make_value(L'e', 5));   
    c2.insert(Myhash_multimap::make_value(L'f', 6));   
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
 **\[d: 4\] \[5\] \[ef 6\]**  
 **\[d: 4\] \[5\] \[ef 6\]**  
 **\[1\] \[2\] \[BC — 3\]**   
## Требования  
 **Заголовок:**\<cliext\/hash\_map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::operator\=](../dotnet/hash-multimap-operator-assign-stl-clr.md)