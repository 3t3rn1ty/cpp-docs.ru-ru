---
title: Ошибка компилятора ресурсов RC2151 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2151
dev_langs:
- C++
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a15f3f1237df9e4b706a2c2048dddd6d5db395d5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109786"
---
# <a name="resource-compiler-error-rc2151"></a>Ошибка компилятора ресурсов RC2151

Невозможно повторно использовать строковые константы

Вы используете то же значение дважды в **STRINGTABLE** инструкции. Убедитесь, что не смешана перекрывающиеся десятичные и шестнадцатеричные значения.

Каждый идентификатор в **STRINGTABLE** должно быть уникальным. Для достижения максимальной эффективности используйте зависимые константы, которые начинаются на кратен 16.