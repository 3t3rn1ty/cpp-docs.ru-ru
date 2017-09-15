---
title: "Шаблоны документов и процесс создания документов и представлений | Microsoft Docs"
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
  - "CDocTemplate - класс"
  - "шаблоны документов, и представления"
  - "архитектура "документ-представление", создание документов и представлений"
  - "значки, для нескольких шаблонов документов"
  - "MFC - библиотека, шаблоны документов"
  - "несколько шаблонов документов"
  - "один шаблон документа"
  - "шаблоны, шаблоны документов"
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Шаблоны документов и процесс создания документов и представлений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для управления сложный процесс создания документов с их связанными представлениями и фреймовыми окнами платформа использует 2 класса шаблона документа. [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) для приложений SDI и [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) для приложений MDI.  `CSingleDocTemplate` может создать и сохранить один документ одного типа одновременно.  `CMultiDocTemplate` сохраняет список нескольких открытых документов одного типа.  
  
 Некоторые приложения поддерживают типы многооконного.  Например, приложение может поддерживать текстовые документы и документы графики.  В этом приложении, когда пользователь выбирает новой команды в меню "Файл" диалогового окна " отображает список возможных новых типов документа, чтобы открыть.  Для каждого поддерживаемого типа документа приложение использует указанный объект шаблона документа.  На следующем рисунке показана конфигурация приложения с интерфейсом MDI, которое поддерживает 2 типа документа и представлено несколько открытых документов.  
  
 ![Приложение MDI, имеющее два типа документов](../mfc/media/vc387h1.png "vc387H1")  
Приложение с интерфейсом MDI с типами 2 документа  
  
 Шаблоны документов создаются и обслуживаются объектом приложения.  Одним из ключевых задач, выполняемых во время функции `InitInstance` приложения построение один или несколько шаблонов документов соответствующего типа.  Эта функция описана в разделе [Создание шаблона документа](../Topic/Document%20Template%20Creation.md).  Объект приложения сохраняет указатель на каждый шаблон документов в списке шаблона и предоставляет интерфейс для добавления шаблоны документов.  
  
 Если необходима поддержка двух или более типов документа, необходимо добавить дополнительный вызов [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) для каждого типа документа.  
  
 Значок регистрируется для всех шаблонов документов на основе его позиции в списке приложений шаблонов документов.  Порядок шаблонов документов определяется порядком они добавляются с вызовами `AddDocTemplate`.  MFC высказывать первый ресурс Значка в приложении значок приложения, следующий ресурс Значка первый Значок документа и т д  
  
 Например, шаблон документов третий 3 для приложения.  Если ресурс Значка в приложении по индексу 3, этот Значок используется для шаблона документа.  Если нет, Значок по индексу 0 используется по умолчанию.  
  
## См. также  
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [Создание шаблонов документов](../Topic/Document%20Template%20Creation.md)   
 [Создание документа или представления](../mfc/document-view-creation.md)   
 [Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)   
 [Создание новых документов, окон и представлений](../Topic/Creating%20New%20Documents,%20Windows,%20and%20Views.md)