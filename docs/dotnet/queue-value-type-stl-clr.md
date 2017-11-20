---
title: "Queue::value_type (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::value_type
dev_langs: C++
helpviewer_keywords: value_type member [STL/CLR]
ms.assetid: f1abde03-982c-4aaf-91a6-cc613df9690e
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eab712aabf524b0fb577fffd6302e54341fe905b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="queuevaluetype-stlclr"></a>queue::value_type (STL/CLR)
Тип элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef Value value_type;  
```  
  
## <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Value`.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_queue_value_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " a b c" using value_type   
    for (; !c1.empty(); c1.pop())   
        {   // store element in value_type object   
        Myqueue::value_type val = c1.front();   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Queue::const_reference (STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)   
 [queue::reference (STL/CLR)](../dotnet/queue-reference-stl-clr.md)