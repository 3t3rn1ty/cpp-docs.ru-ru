---
title: Пример результатов вызова | Документация Майкрософт
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8f09109aab5823f339de76a1337eea77a0794cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037753"
---
# <a name="results-of-calling-example"></a>Пример результатов вызова

**Блок, относящийся только к системам Microsoft**

## <a name="cdecl"></a>__cdecl

— Имя функции на языке C `_MyFunc`.

![Соглашение о вызовах CDECL](../cpp/media/vc37i01.gif "vc37I01") **__cdecl** соглашение о вызовах

## <a name="stdcall-and-thiscall"></a>__stdcall и thiscall

C внутреннее имя (**__stdcall**) является `_MyFunc@20`. Имя C++ декорированные зависит от реализации.

![&#95;&#95;STDCALL и соглашения о вызовах thiscall](../cpp/media/vc37i02.gif "vc37I02") __stdcall и thiscall, соглашения о вызовах

## <a name="fastcall"></a>__fastcall

C внутреннее имя (**__fastcall**) является `@MyFunc@20`. Имя C++ декорированные зависит от реализации.

![Соглашение о вызовах для &#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03") соглашение о вызовах __fastcall

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Пример вызова. Прототип и вызов функции](../cpp/calling-example-function-prototype-and-call.md)