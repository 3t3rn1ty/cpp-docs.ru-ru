---
title: "omp_test_nest_lock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_test_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_test_nest_lock OpenMP function
ms.assetid: 4c909bbe-80e0-4100-aca6-d415d7dc5294
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ba6791c5c5279c82715821d0d32ae7970092319
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="omptestnestlock"></a>omp_test_nest_lock
Пытается установить блокировку, которая, но не блокирует выполнение потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int omp_test_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `lock`  
 Переменная типа [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , инициализированный с [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [3.2.5 функции omp_test_lock и omp_test_nest_lock](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_test_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t nestable_lock;      
  
int main() {  
   omp_init_nest_lock(&nestable_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num();  
      while (!omp_test_nest_lock(&nestable_lock))  
         printf_s("Thread %d - failed to acquire nestable_lock\n",  
                tid);  
  
      printf_s("Thread %d - acquired nestable_lock\n", tid);  
  
      if (omp_test_nest_lock(&nestable_lock)) {  
         printf_s("Thread %d - acquired nestable_lock again\n",  
                tid);  
         printf_s("Thread %d - released nestable_lock\n",   
                tid);  
         omp_unset_nest_lock(&nestable_lock);  
      }  
  
      printf_s("Thread %d - released nestable_lock\n", tid);  
      omp_unset_nest_lock(&nestable_lock);  
   }  
  
   omp_destroy_nest_lock(&nestable_lock);  
}  
```  
  
```Output  
Thread 1 - acquired nestable_lock  
Thread 0 - failed to acquire nestable_lock  
Thread 1 - acquired nestable_lock again  
Thread 0 - failed to acquire nestable_lock  
Thread 1 - released nestable_lock  
Thread 0 - failed to acquire nestable_lock  
Thread 1 - released nestable_lock  
Thread 0 - failed to acquire nestable_lock  
Thread 3 - acquired nestable_lock  
Thread 0 - failed to acquire nestable_lock  
Thread 3 - acquired nestable_lock again  
Thread 0 - failed to acquire nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 3 - released nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 3 - released nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 0 - acquired nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 0 - acquired nestable_lock again  
Thread 2 - failed to acquire nestable_lock  
Thread 0 - released nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 0 - released nestable_lock  
Thread 2 - failed to acquire nestable_lock  
Thread 2 - acquired nestable_lock  
Thread 2 - acquired nestable_lock again  
Thread 2 - released nestable_lock  
Thread 2 - released nestable_lock  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)