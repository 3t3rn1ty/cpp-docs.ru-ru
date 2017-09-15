---
title: "IAccessorImpl::CreateAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IAccessorImpl::CreateAccessor"
  - "CreateAccessor"
  - "ATL::IAccessorImpl::CreateAccessor"
  - "IAccessorImpl.CreateAccessor"
  - "ATL.IAccessorImpl.CreateAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateAccessor - метод"
ms.assetid: f6b92075-c0b8-46ca-8361-026d562d24f5
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IAccessorImpl::CreateAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает метод доступа из набора привязок.  
  
## Синтаксис  
  
```  
  
      STDMETHOD(CreateAccessor)(  
   DBACCESSORFLAGS dwAccessorFlags,  
   DBCOUNTITEM cBindings,  
   const DBBINDING rgBindings[],  
   DBLENGTH cbRowSize,  
   HACCESSOR* phAccessor,  
   DBBINDSTATUS rgStatus[]   
);  
```  
  
#### Параметры  
 В разделе [IAccessor::CreateAccessor](https://msdn.microsoft.com/en-us/library/ms720969.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)   
 [IAccessorImpl::AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)   
 [IAccessorImpl::ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)