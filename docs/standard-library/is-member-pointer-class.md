---
title: Класс is_member_pointer | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_member_pointer
dev_langs:
- C++
helpviewer_keywords:
- is_member_pointer class
- is_member_pointer
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdc179413b3e5d77646be4ccb98f23bcff407fb7
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110270"
---
# <a name="ismemberpointer-class"></a>Класс is_member_pointer

Проверяет, является ли тип указателем на член.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_member_pointer;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является указателем на функцию-член или указатель на объект члена или `cv-qualified` форму одного из них, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_member_pointer.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_member_pointer<trivial *> == "
        << std::boolalpha
        << std::is_member_pointer<trivial *>::value
        << std::endl;
    std::cout << "is_member_pointer<int trivial::*> == "
        << std::boolalpha
        << std::is_member_pointer<int trivial::*>::value
        << std::endl;
    std::cout << "is_member_pointer<int (functional::*)()> == "
        << std::boolalpha
        << std::is_member_pointer<int (functional::*)()>::value
        << std::endl;

    return (0);
    }

```

```Output
is_member_pointer<trivial *> == false
is_member_pointer<int trivial::*> == true
is_member_pointer<int (functional::*)()> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)<br/>
[Класс is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)<br/>
[Класс is_pointer](../standard-library/is-pointer-class.md)<br/>
