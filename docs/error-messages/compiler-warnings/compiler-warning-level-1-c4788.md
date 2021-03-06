---
title: Предупреждение компилятора (уровень 1) C4788 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c8a6ad1aa3ae17944b8c2a292d484d55c24d9cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051741"
---
# <a name="compiler-warning-level-1-c4788"></a>Предупреждение компилятора (уровень 1) C4788

«Идентификатор»: идентификатор усечен до «число» знаков

Компилятор ограничивает максимальную длину имени функции. Когда компилятор создает фанклеты для кода EH/SEH, он формирует имя funclet, добавляя в начало имени функции, с какой-либо текст, например «__catch,» "\__unwind», или другой строкой.

Результирующее имя funclet может быть слишком много времени, и компилятор его и создать C4788.

Чтобы устранить это предупреждение, сократите имя исходной функции. Если функция C++ шаблона функции или метода, используйте определение типа для части имени. Пример:

```
C1<x, y, z<T>>::C2<a,b,c>::f
```

можно заменить:

```
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

Это предупреждение возникает только x64 компилятора.