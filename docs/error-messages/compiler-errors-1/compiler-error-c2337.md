---
title: Ошибка компилятора C2337 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2337
dev_langs:
- C++
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af10023a044e8f4f602ca6a018139d557b99dffe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33195130"
---
# <a name="compiler-error-c2337"></a>Ошибка компилятора C2337
"имя_атрибута": атрибут не найден  
  
 Используется атрибут, который не поддерживается в этой версии Visual C++.  
  
 Следующий пример приводит к возникновению ошибки C2337:  
  
```  
// C2337.cpp  
// compile with: /c  
[emitidl];  
[module(name="x")];  
[grasshopper]   // C2337, not a supported attribute  
class a{};  
```