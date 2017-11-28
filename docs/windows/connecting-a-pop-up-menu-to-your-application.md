---
title: "Подключение к приложению всплывающего меню | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pop-up menus, connecting to applications
- context menus, connecting to applications
- menus, pop-up
- shortcut menus, connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b3e74865f292adf9ba72c36e4bfe9a68e21e32f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="connecting-a-pop-up-menu-to-your-application"></a>Подключение к приложению всплывающего меню
### <a name="to-connect-a-pop-up-menu-to-your-application"></a>Подключение к приложению всплывающего меню  
  
1.  Добавьте обработчик сообщений для WM_CONTEXTMENU (например). Дополнительные сведения см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).  
  
2.  Добавьте в обработчик сообщений следующий код:  
  
    ```  
    CMenu menu;  
    VERIFY(menu.LoadMenu(IDR_MENU1));  
    CMenu* pPopup = menu.GetSubMenu(0);  
    ASSERT(pPopup != NULL);  
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());  
    ```  
  
    > [!NOTE]
    >  [CPoint](../atl-mfc-shared/reference/cpoint-class.md) **передано сообщение обработчика задается в экранных координатах.**  
  

  
 **Requirements**  
  
 MFC  
  
## <a name="see-also"></a>См. также  
 [Создание всплывающих меню](../windows/creating-pop-up-menus.md)   
 [Редактор меню](../windows/menu-editor.md)   