---
title: 'Практическое: объявление спецификаторов переопределения (C + +/ CLI) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1089f2d9326cf268bd76ad59242e2664060b78fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386527"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода (C++/CLI)

[Запечатанный](../windows/sealed-cpp-component-extensions.md), [абстрактный](../windows/abstract-cpp-component-extensions.md), и [переопределить](../windows/override-cpp-component-extensions.md) доступны в компиляциях, не использующих **/ZW** или [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
>  ISO C ++ 11 Standard язык имеет [переопределить](../cpp/override-specifier.md) идентификатор и [окончательный](../cpp/final-specifier.md) идентификатор и оба поддерживаются в Visual Studio используйте `final` вместо `sealed` в коде, который предназначен для скомпилировать как только машинный код.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере показано, что `sealed` является допустимым в компиляции в машинный код.

### <a name="code"></a>Код

```cpp
// sealed_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
   virtual void g();
};

class X : public I1 {
public:
   virtual void g() sealed {}
};

class Y : public X {
public:

   // the following override generates a compiler error
   virtual void g() {}   // C3248 X::g is sealed!
};
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере показано, что `override` является допустимым в компиляции в машинный код.

### <a name="code"></a>Код

```cpp
// override_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
};

class X : public I1 {
public:
   virtual void f() override {}   // OK
   virtual void g() override {}   // C3668 I1::g does not exist
};
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В этом примере показано, что `abstract` является допустимым в компиляции в машинный код.

### <a name="code"></a>Код

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>См. также

[Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)