---
title: "Ошибка компилятора предупреждение (уровень 1) C4052 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4052
dev_langs: C++
helpviewer_keywords: C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b419525d79f1cbda66e16354848348671a3beedc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4052"></a>Предупреждение компилятора (уровень 1) C4052
объявления функции отличаются; одно из них содержит переменные аргументы  
  
 Одно объявление функции не содержит переменных аргументов. Игнорируется.  
  
 В следующем примере возникает ошибка C4052.  
  
```  
// C4052.c  
// compile with: /W4 /c  
int f();  
int f(int i, ...);   // C4052  
```