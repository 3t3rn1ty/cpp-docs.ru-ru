---
title: CManualAccessor::AddParameterEntry | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
dev_langs:
- C++
helpviewer_keywords:
- AddParameterEntry method
ms.assetid: 9048b164-052b-41b1-a861-227fc529e0b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb97e841cf72abcf49ee2a57ccd78832e7fb95a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095945"
---
# <a name="cmanualaccessoraddparameterentry"></a>CManualAccessor::AddParameterEntry
Добавляет запись параметра запись на параметр структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```
void AddParameterEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *справочника программиста OLE DB*.  
  
 `nOrdinal`  
 [in] Номер параметра.  
  
 `wType`  
 [in] Тип данных.  
  
 `nColumnSize`  
 [in] Размер столбца в байтах.  
  
 `pData`  
 [in] Указатель на данные столбцов, сохраненного в буфере.  
  
 `pLength`  
 [in] Указатель длины поля, если это необходимо.  
  
 `pStatus`  
 [in] Указатель на переменную может быть привязано к столбцу "состояние", при необходимости.  
  
 *eParamIO*  
 [in] Указывает, является ли параметр, с которым связан привязку ввода, ввода вывода или выходным параметром.  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать эту функцию, необходимо сначала вызвать [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)   
 [Образец DBViewer](../../visual-cpp-samples.md)