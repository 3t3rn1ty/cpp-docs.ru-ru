---
title: List::generic_value (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::generic_value
dev_langs:
- C++
helpviewer_keywords:
- generic_value member [STL/CLR]
ms.assetid: daa0fc3f-cda2-4531-8cc2-a523737d4103
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7b1e0d73d9a2ef7b5e4ccc35e0ae3242cdf3742f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132441"
---
# <a name="listgenericvalue-stlclr"></a>list::generic_value (STL/CLR)
Тип элемента для использования с универсальный интерфейс для контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для класса контейнера шаблона.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_generic_value.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)   
 [List::generic_iterator (STL/CLR)](../dotnet/list-generic-iterator-stl-clr.md)   
 [list::generic_reverse_iterator (STL/CLR)](../dotnet/list-generic-reverse-iterator-stl-clr.md)