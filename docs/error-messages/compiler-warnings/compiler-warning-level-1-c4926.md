---
title: "Ошибка компилятора предупреждение (уровень 1) C4926 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4926
dev_langs:
- C++
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 07ad4bcc3951615d1eee383807c084958edaf5b4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4926"></a>Предупреждение компилятора (уровень 1) C4926
"идентификатор": символ уже определен: атрибуты игнорируются  
  
 Обнаружено опережающее объявление, но конструкция с атрибутами с тем же именем уже существует. Атрибуты для опережающего объявления игнорируются.  
  
 В следующем примере возникает ошибка C4926.  
  
```  
// C4926.cpp  
// compile with: /W1  
[module(name="MyLib")];  
  
[coclass]  
struct a {  
};  
  
[coclass]  
struct a;   // C4926  
  
int main() {  
}  
```
