---
title: Класс IConvertTypeImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
dev_langs:
- C++
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 09f70e45891e7dc0b07933fe95dce772e5c7159a
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082349"
---
# <a name="iconverttypeimpl-class"></a>Класс IConvertTypeImpl

Предоставляет реализацию [IConvertType](/previous-versions/windows/desktop/ms715926) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
### <a name="parameters"></a>Параметры  

*T*<br/>
Ваш класс, производный от `IConvertTypeImpl`.  

## <a name="requirements"></a>Требования  

**Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[CanConvert](#canconvert)|Сведения о доступности преобразований типа команды или для набора строк.|  
  
## <a name="remarks"></a>Примечания  

Этот интерфейс является обязательным на команды, наборы строк и наборов строк индекса. `IConvertTypeImpl` реализует интерфейс путем делегирования для преобразования объекта, заданного параметром OLE DB.  

## <a name="canconvert"></a> IConvertTypeImpl::CanConvert

Сведения о доступности преобразований типа команды или для набора строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [IConvertType::CanConvert](/previous-versions/windows/desktop/ms711224) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  

Использует преобразования данных OLE DB в `MSADC.DLL`.  
  
## <a name="see-also"></a>См. также  

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)