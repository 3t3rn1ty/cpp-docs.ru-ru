---
title: "Ошибка компилятора C2712 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2712
dev_langs:
- C++
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 89b7d0ad3c7e175db1525c2f3fb8407240ce943c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2712"></a>Ошибка компилятора C2712
Невозможно использовать __try в функциях, требующих уничтожения объектов  
  
 Ошибка C2712 может возникнуть при использовании [/EHsc](../../build/reference/eh-exception-handling-model.md), и функция с структурированной обработки исключений также имеет требующие уничтожение объекты.  
  
 Возможные решения:  
  
-   переместите код, для которого требуется SEH, в другую функцию;  
  
-   заново напишите функции, использующие SEH, чтобы избежать использования локальных переменных и параметров с деструкторами; не используйте SEH в конструкторах и деструкторах;  
  
-   компилируйте код без параметра /EHsc.  
  
 Ошибка C2712 может также возникать, если вызвать метод, объявленный с помощью [__event](../../cpp/event.md) ключевое слово. Поскольку событие может использоваться в многопоточной среде, компилятор создает код, не допускающий использование базового объекта события, а затем включает созданный код в SEH [оператор try-finally](../../cpp/try-finally-statement.md). Поэтому ошибка C2712 может возникнуть, если вызвать метод события и передать аргумент, тип которого содержит деструктор. Одно из решений в данном случае — передача аргумента в качестве константной ссылки.  
  
## <a name="example"></a>Пример  
 C2712 может также возникать, если компиляция выполняется с **/CLR: pure** и объявлении статического массива указателей на функции в `__try` блок. Статический член требует, чтобы компилятор использовал динамическую инициализацию с **/CLR: pure**, что подразумевает обработку исключений C++. Однако обработка исключений C++ не допускается в блоке `__try`.  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора в Visual Studio 2015 являются устаревшими.  
  
 В следующем примере показано возникновение ошибки C2712 и приводятся сведения по ее устранению.  
  
```  
// C2712.cpp  
// compile with: /clr:pure /c  
struct S1 {  
   static int smf();  
   void fnc();  
};  
  
void S1::fnc() {  
   __try {  
      static int (*array_1[])() = {smf,};   // C2712  
  
      // OK  
      static int (*array_2[2])();  
      array_2[0] = smf;  
    }  
    __except(0) {}  
}  
```