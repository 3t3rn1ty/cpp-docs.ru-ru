---
title: auto_gcroot::operator auto_gcroot | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_gcroot.operator auto_gcroot
- auto_gcroot::operator auto_gcroot
- msclr.auto_gcroot.operator auto_gcroot
- msclr::auto_gcroot::operator auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot operator
ms.assetid: 43e3f27a-9f68-444f-9149-a9282a9b935a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dfe81532aa38e79e272e87489a635db66187109b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418220"
---
# <a name="autogcrootoperator-autogcroot"></a>auto_gcroot::operator auto_gcroot

Type-cast-оператор `auto_gcroot` и совместимые типы.

## <a name="syntax"></a>Синтаксис

```
template<typename _other_type>
operator auto_gcroot<_other_type>();
```

## <a name="return-value"></a>Возвращаемое значение

Текущий `auto_gcroot` приведен к `auto_gcroot<_other_type>`.

## <a name="example"></a>Пример

```
// msl_auto_gcroot_op_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
protected:
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {}

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class ClassB : ClassA {
public:
   ClassB( String ^ s) : ClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

int main() {
   auto_gcroot<ClassB^> b = gcnew ClassB("first");
   b->PrintHello();
   auto_gcroot<ClassA^> a = (auto_gcroot<ClassA^>)b;
   a->PrintHello();
}
```

```Output
Hello from first B!
Hello from first A!
```

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\auto_gcroot.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[Члены auto_gcroot](../dotnet/auto-gcroot-members.md)