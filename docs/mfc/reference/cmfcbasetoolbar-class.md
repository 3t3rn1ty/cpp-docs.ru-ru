---
title: "Класс CMFCBaseToolBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseToolBar::CreateObject
- ~CMFCBaseToolBar
- CMFCBaseToolBar
- CMFCBaseToolBar::CMFCBaseToolBar
- CMFCBaseToolBar::~CMFCBaseToolBar
- CMFCBaseToolBar.~CMFCBaseToolBar
- CreateObject
- CMFCBaseToolBar.CMFCBaseToolBar
- CMFCBaseToolBar.CreateObject
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseToolBar class, constructor
- CMFCBaseToolBar class, destructor
- ~CMFCBaseToolBar destructor
- CreateObject method
- CMFCBaseToolBar class
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f608b23c0dbee3ec0e2d2b234612365e3c2461b0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbasetoolbar-class"></a>Класс CMFCBaseToolBar
Базовый класс для панели инструментов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCBaseToolBar : public CPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCBaseToolBar::CMFCBaseToolBar`|Конструктор по умолчанию.|  
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCBaseToolBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|Возвращает режим закрепления. (Переопределяет [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).)|  
|[CMFCBaseToolBar::GetMinSize](#getminsize)|Возвращает минимальный размер панели инструментов. (Переопределяет [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CMFCBaseToolBar::OnAfterChangeParent](#onafterchangeparent)|Вызывается платформой после изменения родительской области. (Переопределяет [CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbasetoolbar.h  
  
##  <a name="a-namegetdockingmodea--cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a>CMFCBaseToolBar::GetDockingMode  
 Возвращает режим закрепления.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Режим закрепления.  
  
##  <a name="a-namegetminsizea--cmfcbasetoolbargetminsize"></a><a name="getminsize"></a>CMFCBaseToolBar::GetMinSize  
 Возвращает минимальный размер панели инструментов.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `size`  
 Минимальный размер панели инструментов.  
  
##  <a name="a-nameonafterchangeparenta--cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a>CMFCBaseToolBar::OnAfterChangeParent  
 Вызывается платформой после изменения родительской области.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndOldParent`  
 Указатель на предыдущем родительского окна.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

