---
title: Ошибка компилятора C3459 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3459
dev_langs:
- C++
helpviewer_keywords:
- C3459
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abde90828cac4f45685b7a21b50705474aedde72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026794"
---
# <a name="compiler-error-c3459"></a>Ошибка компилятора C3459

"атрибут": атрибут допустим только в индексаторе класса (индексированное свойство по умолчанию)

Атрибут, создаваемый для применения к свойству индексатора класса, использован неправильно.

Дополнительные сведения см. в разделе [как: используйте свойства в C + +/ CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3459.

```
// C3459.cpp
// compile with: /clr /c
public ref class MyString {
public:
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459
   property int Prop;
};

// OK
public ref class MyString2 {
   array<int>^ MyArr;
public:
   MyString2() {
      MyArr = gcnew array<int>(5);
   }

   [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK
   property int default[int] {
      int get(int index) {
         return MyArr[index];
      }
      void set(int index, int value) {
         MyArr[index] = value;
      }
   }
};
```