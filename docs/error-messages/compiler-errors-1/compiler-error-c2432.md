---
title: "Ошибка компилятора C2432 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 574b0aa7ac1ca79d3a1c50c37319e53e7fd6b7ad
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2432"></a>Ошибка компилятора C2432
Недопустимая ссылка на 16-битные данные в «идентификатор»  
  
 16-битный регистр используется как индекс или базового регистра. Компилятор не поддерживает ссылки на 16-битные данные. 16-разрядные регистры не может использоваться в качестве индексных или базовых при компиляции для 32-разрядного кода.  
  
 Следующий пример приводит к возникновению ошибки C2432:  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```