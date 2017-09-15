---
title: "Изменение масштаба и прокрутка представлений | Microsoft Docs"
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
  - "обработчики сообщений"
  - "обработка сообщений, полосы прокрутки в классе представления"
  - "масштабирование представлений"
  - "полосы прокрутки, сообщения"
  - "представления прокрутки"
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Изменение масштаба и прокрутка представлений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC поддерживает представления, — и представления, автоматически масштабируется в соответствии с размером фреймового окна, в котором будут отображаться.  Класс `CScrollView` поддерживает оба типа представления.  
  
 Дополнительные сведения о прокрутя и класс масштабируя см. в разделе [CScrollView](../mfc/reference/cscrollview-class.md) в *справочнике по MFC*.  Пример прокрутки см. в разделе [Образец Scribble](../top/visual-cpp-samples.md).  
  
## Дополнительные сведения  
  
-   Прокрутить представление  
  
-   Масштабирование представления  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f321fcf7c88bc6e3f892ae0fc9b2f0d8" class\="tgtSentence"\>Координаты представления\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> Прокрутить представление  
 Часто размер документа превышает размер его представление может отобразить.  Это может произойти, так как данные документа увеличивают окно пользователь или уменьшите это представление кадров.  В таких случаях представление должно поддерживать прокрутки.  
  
 Любое представление может обрабатывать сообщения полосы прокрутки в его функций\-членов `OnHScroll` и `OnVScroll`.  Можно реализовать обработку сообщений полосы прокрутки в этих функциях, создание всего рабочего самостоятельно, или можно использовать класс `CScrollView` обработки прокрутка автоматически.  
  
 Объект `CScrollView` выполняет следующие действия.  
  
-   Управление размеры окна и окна просмотра и режимы сопоставления  
  
-   Прокрутки автоматически в ответ на сообщения полосы прокрутки  
  
 Можно указать как для прокрутки для «страницы» \(при нажатии на основании полосы прокрутки\) и «линия» \(при нажатии на кнопку со стрелкой для прокрутки\).  Планирование этих значений в соответствии с требованиями природа данного представления.  Например, может понадобиться переход на 1 пиксель для представления графика, но в сегментами, основанных на высоте линии в текстовых документах.  
  
##  <a name="_core_scaling_a_view"></a> Масштабирование представления  
 При необходимости представление автоматически адаптация размер его фреймового окна, можно использовать `CScrollView` для масштабирования вместо прокрутки.  Логическое представление или на то растянуто для точного соответствия клиентской области окна.  Масштабированное представление не содержит полосы прокрутки.  
  
## См. также  
 [Использование представлений](../mfc/using-views.md)