---
title: Предупреждение компилятора (уровень 3) C4535 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4535
dev_langs:
- C++
helpviewer_keywords:
- C4535
ms.assetid: 2c5ad1aa-2558-41d1-8f06-47fef74c8d9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56d6771bbe4db9d906fb9efddc6134c8e7dda2b8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096721"
---
# <a name="compiler-warning-level-3-c4535"></a>Предупреждение компилятора (уровень 3) C4535

для Calling _set_se_translator() требуется/EHa

Использование [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) требует [/EHa](../../build/reference/eh-exception-handling-model.md) параметр компилятора и не **/EHs**.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4535.

```
// C4535.cpp
// compile with: /W3 /EHsc /c
// C4535 expected
// to fix, compile with /EHa instead
#include <stdio.h>
#include <windows.h>
#include <eh.h>

void SEFunc();
void trans_func( unsigned int, EXCEPTION_POINTERS* );

class SE_Exception {
private:
   unsigned int nSE;
public:
   SE_Exception() {}
   SE_Exception( unsigned int n ) : nSE( n ) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() { return nSE; }
};

int main() {
   try {
      _set_se_translator( trans_func );
      SEFunc();
   }
   catch( SE_Exception e ) {
      printf_s( "Caught a __try exception with SE_Exception.\n" );
   }
}

void SEFunc() {
   __try {
      int x, y=0;
      x = 5 / y;
   }
   __finally {
      printf_s( "In finally\n" );
   }
}

void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp ) {
   printf_s( "In trans_func.\n" );
   throw SE_Exception();
}
```