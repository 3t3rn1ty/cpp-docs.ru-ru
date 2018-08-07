---
title: Метод RuntimeClass::InternalAddRef | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
dev_langs:
- C++
helpviewer_keywords:
- InternalAddRef method
ms.assetid: b8ed7f93-83d8-47ec-988c-98fe65104e7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 52a594b0731ec8b22076a422fec4cb52c3503235
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603085"
---
# <a name="runtimeclassinternaladdref-method"></a>Метод RuntimeClass::InternalAddRef
Увеличивает счетчик ссылок для текущего **RuntimeClass** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ULONG InternalAddRef();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Итоговый счетчик ссылок.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)