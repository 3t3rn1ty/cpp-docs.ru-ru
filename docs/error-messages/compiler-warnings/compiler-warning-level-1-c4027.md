---
title: Предупреждение компилятора (уровень 1) C4027 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4027
dev_langs:
- C++
helpviewer_keywords:
- C4027
ms.assetid: f30d57b9-20c4-4284-8686-566d9f0ca7fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b919eeece5529d1914fadf5724088e3e64e73db9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089519"
---
# <a name="compiler-warning-level-1-c4027"></a>Предупреждение компилятора (уровень 1) C4027

функция объявлена без списка формальных параметров

В объявлении функции отсутствуют формальные параметры, но существуют формальные параметры в определении функции или фактические параметры в вызове. При последующих вызовах этой функции предполагается, что функция принимает фактические параметры типов, найденных в определении функции или в вызове.