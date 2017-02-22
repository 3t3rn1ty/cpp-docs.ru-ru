---
title: "private (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "private"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "private OpenMP clause"
ms.assetid: 772904a2-1345-4562-90e6-eb4dc85aea1a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# private (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает, что каждый поток должен иметь собственный экземпляр переменной.  
  
## Синтаксис  
  
```  
private(var)  
```  
  
## Заметки  
 Здесь:  
  
 `var`  
 Переменная, чтобы получить экземпляры в каждом потоке.  
  
## Заметки  
 **private** применяется к следующим рекомендациям:  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../Topic/single.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.1 private](../../../parallel/openmp/2-7-2-1-private.md).  
  
## Пример  
  
```  
// openmp_private.c  
// compile with: /openmp  
#include <windows.h>  
#include <assert.h>  
#include <stdio.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define SLEEP_THREAD 1  
#define NUM_LOOPS 2  
  
enum Types {  
   ThreadPrivate,  
   Private,  
   FirstPrivate,  
   LastPrivate,  
   Shared,  
   MAX_TYPES  
};  
  
int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};  
int nThreadPrivate;  
  
#pragma omp threadprivate(nThreadPrivate)  
#pragma warning(disable:4700)  
  
int main() {  
   int nPrivate = NUM_THREADS;  
   int nFirstPrivate = NUM_THREADS;  
   int nLastPrivate = NUM_THREADS;  
   int nShared = NUM_THREADS;  
   int nRet = 0;  
   int i;  
   int j;  
   int nLoop = 0;  
  
   nThreadPrivate = NUM_THREADS;  
   printf_s("These are the variables before entry "  
           "into the parallel region.\n");  
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);  
   printf_s("      nPrivate = %d\n", nPrivate);  
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);  
   printf_s("  nLastPrivate = %d\n", nLastPrivate);  
   printf_s("       nShared = %d\n\n", nShared);  
   omp_set_num_threads(NUM_THREADS);  
  
   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)  
   {  
      #pragma omp for schedule(static) lastprivate(nLastPrivate)  
      for (i = 0 ; i < NUM_THREADS ; ++i) {  
         for (j = 0 ; j < NUM_LOOPS ; ++j) {  
            int nThread = omp_get_thread_num();  
            assert(nThread < NUM_THREADS);  
  
            if (nThread == SLEEP_THREAD)  
               Sleep(100);  
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;  
            nSave[nThread][Private][j] = nPrivate;  
            nSave[nThread][Shared][j] = nShared;  
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;  
            nSave[nThread][LastPrivate][j] = nLastPrivate;  
            nThreadPrivate = nThread;  
            nPrivate = nThread;  
            nShared = nThread;  
            nLastPrivate = nThread;  
            --nFirstPrivate;  
         }  
      }  
   }  
  
   for (i = 0 ; i < NUM_LOOPS ; ++i) {  
      for (j = 0 ; j < NUM_THREADS ; ++j) {  
         printf_s("These are the variables at entry of "  
                  "loop %d of thread %d.\n", i + 1, j);  
         printf_s("nThreadPrivate = %d\n",  
                  nSave[j][ThreadPrivate][i]);  
         printf_s("      nPrivate = %d\n",  
                  nSave[j][Private][i]);  
         printf_s(" nFirstPrivate = %d\n",  
                  nSave[j][FirstPrivate][i]);  
         printf_s("  nLastPrivate = %d\n",  
                  nSave[j][LastPrivate][i]);  
         printf_s("       nShared = %d\n\n",  
                  nSave[j][Shared][i]);  
      }  
   }  
  
   printf_s("These are the variables after exit from "  
            "the parallel region.\n");  
   printf_s("nThreadPrivate = %d (The last value in the "  
            "master thread)\n", nThreadPrivate);  
   printf_s("      nPrivate = %d (The value prior to "  
            "entering parallel region)\n", nPrivate);  
   printf_s(" nFirstPrivate = %d (The value prior to "  
            "entering parallel region)\n", nFirstPrivate);  
   printf_s("  nLastPrivate = %d (The value from the "  
            "last iteration of the loop)\n", nLastPrivate);  
   printf_s("       nShared = %d (The value assigned, "  
            "from the delayed thread, %d)\n\n",  
            nShared, SLEEP_THREAD);  
}  
```  
  
  **Эти переменные перед записью в параллельной области.  nThreadPrivate \= 4**  
 **nPrivate \= 4**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 4**  
 **nShared \= 4**  
**Эти переменные на записи цикла 1 потока 0.  nThreadPrivate \= 4**  
 **nPrivate \= 1310720**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 1245104**  
 **nShared \= 3**  
**Эти переменные на записи цикла 1 потоков на 1.  nThreadPrivate \= 4**  
 **nPrivate \= 4488**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 19748**  
 **nShared \= 0**  
**Эти переменные на записи цикла 1 потоков на 2.  nThreadPrivate \= 4**  
 **nPrivate \= \-132514848**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= \-513199792**  
 **nShared \= 4**  
**Эти переменные на записи цикла 1 потоков на 3.  nThreadPrivate \= 4**  
 **nPrivate \= 1206**  
 **nFirstPrivate \= 4**  
 **nLastPrivate \= 1204**  
 **nShared \= 2**  
**Эти переменные на записи цикла 2 потока 0.  nThreadPrivate \= 0**  
 **nPrivate \= 0**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 0**  
 **nShared \= 0**  
**Эти переменные на записи цикла 2 потоков на 1.  nThreadPrivate \= 1**  
 **nPrivate \= 1**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 1**  
 **nShared \= 1**  
**Эти переменные на записи цикла 2 потоков на 2.  nThreadPrivate \= 2**  
 **nPrivate \= 2**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 2**  
 **nShared \= 2**  
**Эти переменные на записи цикла 2 потоков на 3.  nThreadPrivate \= 3**  
 **nPrivate \= 3**  
 **nFirstPrivate \= 3**  
 **nLastPrivate \= 3**  
 **nShared \= 3**  
**Эти переменные выберите оставить от параллельной области.  nThreadPrivate \= 0 \(последнее значение в главном потоке\)**  
 **nPrivate \= 4 \(значение вставка параллельной области\)**  
 **nFirstPrivate \= 4 \(значение вставка параллельной области\)**  
 **nLastPrivate \= 3 \(с последней итерации цикла\)**  
 **nShared \= 1 \(значение, присвоенное из задержанного потока, 1\)**    
## См. также  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)