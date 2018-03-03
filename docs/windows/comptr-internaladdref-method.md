---
title: "Метод ComPtr::InternalAddRef | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::InternalAddRef
dev_langs:
- C++
helpviewer_keywords:
- InternalAddRef method
ms.assetid: f8e860ef-c56e-42a6-a712-77aaab1464ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 52e6b3f0ba32aa967cef6ec632db7ed14eb4c4c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="comptrinternaladdref-method"></a>Метод ComPtr::InternalAddRef
Увеличивает счетчик ссылок интерфейса, связанного с этим объектом ComPtr.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void InternalAddRef() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Этот метод защищен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)