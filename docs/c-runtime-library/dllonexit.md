---
title: "__dllonexit | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- __dllonexit
dev_langs:
- C++
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 147458732658b5e08efa880fc9e7e76ebcd7da63
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="dllonexit"></a>__dllonexit
Регистрирует подпрограмму, вызываемую во время выхода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_onexit_t __dllonexit(   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### <a name="parameters"></a>Параметры  
 `func`  
 Указатель на функцию, которая должна выполняться при выходе.  
  
 `pbegin`  
 Указатель на переменную, указывающую на начало списка функций, которые должны выполняться при отключении.  
  
 `pend`  
 Указатель на переменную, указывающую на конец списка функций, которые должны выполняться при отключении.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращается указатель на функцию пользователя. В противном случае возвращается указатель NULL.  
  
## <a name="remarks"></a>Примечания  
 Функция `__dllonexit` аналогична функции [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) за тем исключением, что глобальные переменные, которые она использует, не видны подпрограмме. Вместо глобальных переменных в этой функции применяются параметры `pbegin` и `pend`.  
  
 Функции `_onexit` и `atexit` в библиотеке DLL, связанной с файлом MSVCRT.LIB, должны содержать собственный список atexit/_onexit. Эта подпрограмма представляет собой рабочий процесс, который вызывают такие библиотеки DLL.  
  
 Тип `_PVFV` определяется как `typedef void (__cdecl *_PVFV)(void)`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный файл|  
|-------------|-------------------|  
|__dllonexit|onexit.c|  
  
## <a name="see-also"></a>См. также  
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)