---
title: omp_get_wtime | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_wtime
dev_langs:
- C++
helpviewer_keywords:
- omp_get_wtime OpenMP function
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2d02bf5b8de0094a18d456a569b24fed2e03b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391765"
---
# <a name="ompgetwtime"></a>omp_get_wtime

Возвращает значение в секундах времени, прошедшего с какой-то момент.

## <a name="syntax"></a>Синтаксис

```
double omp_get_wtime( );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает значение в секундах времени, прошедшего с некоторые произвольной, но согласованные точки.

## <a name="remarks"></a>Примечания

Во время выполнения программы, выполнения последующих сравнений возможных этой точки будет оставаться неизменным.

Дополнительные сведения см. в разделе [3.3.1 функция omp_get_wtime](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).

## <a name="example"></a>Пример

```
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)