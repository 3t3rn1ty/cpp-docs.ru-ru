---
title: "hash_multimap::const_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::const_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_iterator - элемент [STL/CLR]"
ms.assetid: 3d54185c-7d30-41e6-8837-92e62448bc8e
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# hash_multimap::const_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип постоянного итератора для управляемой последовательности.  
  
## Синтаксис  
  
```  
typedef T2 const_iterator;  
```  
  
## Заметки  
 Описывает тип объекта неспецифицированного типа `T2`, который можно использовать как постоянный двунаправленный итератор для контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_hash_multimap_const_iterator.cpp   
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
    Myhash_multimap::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" [{0} {1}]", cit->first, cit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**   
## Требования  
 **Заголовок:**\<cliext\/hash\_map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::iterator](../dotnet/hash-multimap-iterator-stl-clr.md)