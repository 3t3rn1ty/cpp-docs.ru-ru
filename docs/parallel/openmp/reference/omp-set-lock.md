---
title: функции omp_set_lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_lock OpenMP function
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59a7bcc24b67e916271748740dd88568979d5a70
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401606"
---
# <a name="ompsetlock"></a>omp_set_lock

Блокирует выполнение потока, пока не станет доступна блокировка.

## <a name="syntax"></a>Синтаксис

```
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , инициализированный с [функции omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.3 функции omp_set_lock и omp_set_nest_lock функции](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

## <a name="examples"></a>Примеры

См. в разделе [функции omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) пример использования `omp_set_lock`.

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)