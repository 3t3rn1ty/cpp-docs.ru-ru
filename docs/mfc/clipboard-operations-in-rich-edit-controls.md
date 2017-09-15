---
title: "Операции буфера обмена с использованием элементов управления &quot;Rich Edit&quot; | Microsoft Docs"
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
  - "буфер обмена, операции в CRichEditCtrl"
  - "операции копирования в элементах управления редактированием с форматированием"
  - "CRichEditCtrl - класс, Clipboard - операции"
  - "CRichEditCtrl - класс, операция вставки"
  - "операция вырезания в классе CRichEditCtrl"
  - "вставка данных из буфера обмена"
  - "элементы управления Rich Edit, Clipboard - операции"
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Операции буфера обмена с использованием элементов управления &quot;Rich Edit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приложение может вставить содержимое буфера обмена в элемент управления расширенного редактирования \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\), используя либо доступны наилучший формат обмена или формат буфера обмена.  Можно также определить, является ли элемент управления расширенного редактирования способно вставить формат буфера обмена.  
  
 Можно скопировать или вырезать содержимое текущего выделения с помощью функции\-члена [Копировать](../Topic/CRichEditCtrl::Copy.md) или [Вырезать](../Topic/CRichEditCtrl::Cut.md).  Аналогичным образом можно вставить содержимое буфера обмена в элемент управления расширенного редактирования с помощью функции\-члена [Вставить](../Topic/CRichEditCtrl::Paste.md).  Элемент управления вставьте первый доступны, он распознает формат, который предположительно является описательный формат.  
  
 Чтобы вставить формат буфера обмена можно использовать функцию\-член [PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md).  Эта функция полезна для приложений с помощью команды для вставки, которая позволяет пользователю выбрать формат буфера обмена.  Можно использовать функцию\-член [CanPaste](../Topic/CRichEditCtrl::CanPaste.md), чтобы определить, является ли заданный формат элементом управления.  
  
 Можно также использовать `CanPaste` определить, является ли любой доступный формат обмена элемента управления расширенного редактирования.  Эта функция полезна в обработчике `OnInitMenuPopup`.  Приложение может включить или серый цвет его команду " в зависимости от того, является ли элемент управления может вставить любой доступный формат.  
  
 Форматы обмена регистр 2 элементами управления расширенного редактирования: формат текст RTF и формат, текст и объекты RichEdit.  Приложение может зарегистрировать эти форматы с помощью функции [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049), указывая значения **CF\_RTF** и **CF\_RETEXTOBJ**.  
  
## См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)