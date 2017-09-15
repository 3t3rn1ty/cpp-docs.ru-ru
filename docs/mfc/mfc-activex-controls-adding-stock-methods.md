---
title: "Элементы управления ActiveX в MFC. Добавление стандартных методов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoClick - метод"
  - "MFC ActiveX - элементы управления, методы"
  - "MFC ActiveX - элементы управления, методы хранения"
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Элементы управления ActiveX в MFC. Добавление стандартных методов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Стандартный метод отличается от пользовательского метода, так как он уже реализован классом [COleControl](../mfc/reference/colecontrol-class.md).  Например, `COleControl` содержит предопределенный функции\-члена, поддерживающим метод обновления для элемента управления.  Запись схемы подготовки к отправке этого стандартного метода **DISP\_STOCKFUNC\_REFRESH**.  
  
 `COleControl` поддерживает 2 стандартного метода: DoClick и обновления.  Refresh вызывается пользователем элемента управления непосредственно для обновления внешний вид элемента управления; DoClick вызывается порождения события click элемента управления.  
  
|Метод|Запись схемы подготовки к отправке|Комментарий|  
|-----------|----------------------------------------|-----------------|  
|`DoClick`|**DISP\_STOCKPROP\_DOCLICK \(\)**|Вызывает событие click.|  
|**Обновить**|**DISP\_STOCKPROP\_REFRESH \(\)**|Немедленно обновляет внешний вид элемента управления.|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a> Добавление стандартный метод с помощью мастера добавления метода.  
 Добавление стандартный метод простым с помощью [Мастер добавления метода](../ide/add-method-wizard.md).  В следующей процедуре показано добавление метод обновления на элемент управления, созданный с помощью мастера элементов управления ActiveX MFC.  
  
#### Чтобы добавить биржевая обновление метода с помощью мастера добавления метода.  
  
1.  Загрузите проект элемента управления.  
  
2.  В представлении классов разверните узел библиотеки элемента управления.  
  
3.  Щелкните правой кнопкой мыши узел интерфейса для элемента управления \(второго узла узла библиотеки\), чтобы открыть контекстное меню.  
  
4.  В контекстном меню щелкните **Добавить**, а затем щелкните **Добавить метод**.  
  
     Это будет открыт мастер добавления метода.  
  
5.  В поле **Имя метода**, нажмите **Обновить**.  
  
6.  Нажмите кнопку **Готово**.  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a> Добавьте мастера изменения метода для стандартных методов  
 Поскольку биржевая обновление поддерживается метод базового класса элемента управления **Мастер добавления метода**, не изменяет объявление класса элемента управления в любом случае.  Он добавляет запись для метода в схеме подготовки к отправке элемента управления и его файл .IDL.  В следующей линия добавляется в схеме подготовки к отправке элемента управления, находящуюся в его файле реализации \(CPP\).  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 Это делает доступными для пользователей метод обновления элемента управления.  
  
 В следующей линия добавляется в файл .IDL элемента управления:  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 Эта линия присвоить метод обновления определенный идентификатор.  
  
## См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)