---
title: "ЛОКАЛЬНЫЙ (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 037baa2032902060f6dc3e7ab3e54d95dd0922aa
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="local-masm"></a>LOCAL (MASM)
В директиве первого макроса **ЛОКАЛЬНОГО** определяет метки, которые являются уникальными для каждого экземпляра макроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>Примечания  
 В директиве второй в определении процедуры (**PROC**), **ЛОКАЛЬНОГО** создает стековую переменные, которые существуют во время процедуры. *Метка* может быть простой переменной или массив, содержащий *число* элементов.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)