---
title: "Класс allocator_variable_size | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators::allocator_variable_size
- allocators/stdext::allocator_variable_size
- allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
dev_langs:
- C++
helpviewer_keywords:
- allocator_variable_size class
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 67073d663f21d6e62898e3f06ad1fb66527db21d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="allocatorvariablesize-class"></a>Класс allocator_variable_size
Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_variable_size](../standard-library/max-variable-size-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Type>  
class allocator_variable_size;
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Type`|Тип элементов, распределяемых распределителем.|  
  
## <a name="remarks"></a>Примечания  
 Макрос [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) передает этот класс как параметр `name` в следующей инструкции: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)



