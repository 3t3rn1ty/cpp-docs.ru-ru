---
title: __indword | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __indword_cpp
- __indword
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 554cccba1d45cf172645c46e00fdb20c19ea42d4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389607"
---
# <a name="indword"></a>__indword

**Блок, относящийся только к системам Microsoft**

Считывает один двойное слово данных из указанного порта с помощью `in` инструкции.

## <a name="syntax"></a>Синтаксис

```
unsigned long __indword(
   unsigned short Port
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для чтения из.

## <a name="return-value"></a>Возвращаемое значение

Слово, прочитанное из порта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__indword`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)