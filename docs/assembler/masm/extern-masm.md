---
title: EXTERN (MASM) | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- extern
dev_langs:
- C++
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a9008e8c1153c0a9b06530b14e661436f7e62a9
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693674"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Определяет один или несколько внешних переменных, меток или символов, которые называются *имя* типом *тип*.

## <a name="syntax"></a>Синтаксис

> EXTERN [[*langtype*]] *имя* [[(*altid*)]]: *тип* [[, [[*langtype*]]  *имя* [[(*altid*)]]: *тип*]]...

## <a name="remarks"></a>Примечания

*Тип* может быть [ABS](../../assembler/masm/operator-abs.md), которая импортирует *имя* как константа. Совпадение с кодом [EXTRN](../../assembler/masm/extrn.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>