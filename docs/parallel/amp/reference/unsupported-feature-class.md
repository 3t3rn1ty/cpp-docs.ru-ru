---
title: "Класс unsupported_feature | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
dev_langs:
- C++
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4be595382436f26ed43215c86d3f350532c52af
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="unsupportedfeature-class"></a>Класс unsupported_feature
Исключение, возникающее при использовании неподдерживаемой возможности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор unsupported_feature](#ctor)|Создает новый экземпляр класса `unsupported_feature` исключение.|  

  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## <a name="unsupported_feature__ctor"></a> unsupported_feature 

  Создает новый экземпляр исключения unsupported_feature.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описание ошибки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `unsupported_feature`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
