---
title: Предупреждение (уровень 1) C4142 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c87b7689cf11ab28c1a6377ff85e1594fd1b5fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284437"
---
# <a name="compiler-warning-level-1-c4142"></a>Предупреждение (уровень 1) C4142 компилятора
неопасное переопределение типа  
  
 Тип переопределяется таким образом, чтобы не влияет на созданный код.  
  
 Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
-   Функции-члена производного класса имеет другой тип возвращаемого значения из соответствующей функции-члена базового класса.  
  
-   Тип, определенный с `typedef` переопределен с помощью различный синтаксис команды.  
  
 Следующий пример приводит к возникновению ошибки C4142:  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```