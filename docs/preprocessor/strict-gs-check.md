---
title: strict_gs_check | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
dev_langs:
- C++
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6797e9a75e9150718655ed7fcd72d7f343e591
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430206"
---
# <a name="strictgscheck"></a>strict_gs_check
Эта директива #pragma обеспечивает усиленную проверку безопасности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## <a name="remarks"></a>Примечания  
 
Заставляет компилятор вставлять случайные объекты cookie в стек функции, помогая обнаруживать некоторые категории переполнения буфера на основе стека. По умолчанию `/GS` параметр компилятора (проверка безопасности буфера) обеспечивает вставку объектов cookie для всех функций. Дополнительные сведения см. в разделе [Параметр /GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md).  
  
Необходимо выполнять компиляцию с `/GS` (проверка безопасности буфера) для включения **strict_gs_check**.  
  
Используйте эту директиву #pragma в модулях кода, которые могут получать потенциально вредоносные данные. Эта директива #pragma отличается очень агрессивным поведением и применяется к функциям, для которых подобная защита может не требоваться, но оптимизирована с целью минимального влияния на производительность конечного приложения.  
  
Даже при использовании этой директивы #pragma следует стремиться к созданию защищенного программного кода. То есть убедитесь в том, что код содержит без переполнения буфера. **strict_gs_check** может помочь защитить приложение от ошибок переполнения буфера, которые остаются в коде.  
  
## <a name="example"></a>Пример  
 
В следующем коде переполнение буфера возникает при копировании массива в локальный массив. При компиляции этого кода с помощью `/GS`, cookie не помещаются в стек, так как тип данных массива является указателем. Добавление **strict_gs_check** pragma заставляет cookie стека в стек функции.  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
```  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md)