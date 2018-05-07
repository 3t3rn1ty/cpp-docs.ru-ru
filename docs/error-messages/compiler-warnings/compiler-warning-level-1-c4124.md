---
title: Предупреждение (уровень 1) C4124 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: accd58c123bcd74e54176eed5eb974c3df33dbab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4124"></a>Предупреждение (уровень 1) C4124 компилятора
__fastcall с проверкой стека неэффективно  
  
 `__fastcall` Было использовано ключевое слово при включенном режиме проверки стека.  
  
 `__fastcall` Соглашение создает код быстрее, но проверка стека замедляет. При использовании `__fastcall`, отключить проверку стека с **check_stack** pragma или/GS.  
  
 Это предупреждение выдается только для первой функции, объявленной в этих условиях.