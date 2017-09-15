---
title: "Планировщик задач (среда выполнения с параллелизмом) | Microsoft Docs"
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
  - "упрощенные задачи [среда выполнения с параллелизмом]"
  - "превышение лимита подписки [среда выполнения с параллелизмом]"
  - "группы расписаний [среда выполнения с параллелизмом]"
  - "экземпляры планировщика [среда выполнения с параллелизмом]"
  - "политики планировщика [среда выполнения с параллелизмом]"
  - "планировщик задач [среда выполнения с параллелизмом]"
  - "планировщик задач [среда выполнения с параллелизмом], упрощенные задачи"
  - "планировщик задач [среда выполнения с параллелизмом], превышение лимита подписки"
  - "планировщик задач [среда выполнения с параллелизмом], группы расписаний"
  - "планировщик задач [среда выполнения с параллелизмом], экземпляры планировщика"
  - "планировщик задач [среда выполнения с параллелизмом], политики планировщика"
  - "планировщик задач [среда выполнения с параллелизмом], wait - функция"
  - "wait - функция [среда выполнения с параллелизмом]"
ms.assetid: 9aba278c-e0c9-4ede-b7c6-fedf7a365d90
caps.latest.revision: 42
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 41
---
# Планировщик задач (среда выполнения с параллелизмом)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Подразделы в этом разделе документации описывают важные функции планировщика заданий исполняющей среды с параллелизмом.  Планировщик задач удобно использовать, когда нужно оптимизировать производительность существующего кода, использующего среду выполнения с параллелизмом.  
  
> [!IMPORTANT]
>  Планировщик заданий не доступен из приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения см. в разделе [Создание асинхронных операций в C\+\+ для приложений для Магазина Windows](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
>   
>  В Visual Studio 2015 и более поздних версиях класс [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) и связанные типы в файле ppltasks.h используют Windows ThreadPool в качестве своего планировщика.  Этот раздел больше не относится к типам, определенным в файле ppltasks.h.  Параллельные алгоритмы, например parallel\_for, продолжают по умолчанию использовать планировщик среды выполнения с параллелизмом.  
  
> [!TIP]
>  Среда выполнения с параллелизмом предоставляет планировщик по умолчанию, и таким образом не требуется создавать планировщик в приложении.  Поскольку планировщик задач помогает оптимизировать производительность приложений, рекомендуется начать с [Библиотека параллельных шаблонов](../../parallel/concrt/parallel-patterns-library-ppl.md) или [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md), если вы не имеете опыта работы в среде выполнения с параллелизмом.  
  
 Планировщик задач планирует и координирует задачи во время выполнения.  *Задача* — это единица работы, которая выполняет конкретное задание.  Обычно задача выполняется параллельно с другими задачами.  В качестве примеров задач можно назвать работу, выполняемую элементами группы задач, параллельными алгоритмами и асинхронными агентами.  
  
 Планировщик задач осуществляет управление сведениями, связанными с эффективным планированием задач на компьютерах с большим объемом вычислительных ресурсов.  Планировщик задач также использует новейшие возможности базовой операционной системы.  Таким образом, приложения, использующие среду выполнения с параллелизмом, автоматически масштабируются и совершенствуются на оборудовании с расширенными возможностями.  
  
 В разделе [Сравнение с другими моделями параллелизма](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md) описываются различия между механизмами приоритетного планирования и координированного планирования.  Планировщик заданий использует координированное планирование и алгоритм перехвата работы вместе с планировщиком с приоритетами операционной системы, чтобы максимально эффективно использовать ресурсы для обработки.  
  
 Среда выполнения с параллелизмом предоставляет планировщик по умолчанию, поэтому нет необходимости управлять деталями инфраструктуры.  Поэтому планировщик обычно не используется напрямую.  Однако для удовлетворения качественных требований приложения вы можете с помощью планировщика задач предоставить собственную политику планирования или связать планировщики с конкретными задачами.  Например, предположим, что имеется подпрограмма параллельной сортировки, которая не может использовать более четырех процессоров.  С помощью *политики планировщика* вы можете создать планировщик, который формирует не более четырех параллельных задач.  Выполнение подпрограммы сортировки в данном планировщике позволит другим активным планировщикам использовать все остающиеся вычислительные ресурсы.  
  
## См. также  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[Экземпляры планировщика](../../parallel/concrt/scheduler-instances.md)|В этом разделе описываются экземпляры планировщиков и использование классов `concurrency::Scheduler` и `concurrency::CurrentScheduler` для управления ими.  Используйте экземпляры планировщика, когда требуется связать явные политики планирования с определенными типами рабочих нагрузок.|  
|[Политики планировщика](../../parallel/concrt/scheduler-policies.md)|В этом разделе описывается роль политик планировщика.  Используйте политики планировщика, если нужно управлять стратегией, которую планировщик применяет при управлении задачами.|  
|[Группы расписаний](../../parallel/concrt/schedule-groups.md)|В этом разделе описывается роль групп расписаний.  Используйте группы расписаний, когда требуется высокая степень локальности связанных задач, например если группу связанных задач лучше выполнять в одном узле процессора.|  
|[Упрощенные задачи](../../parallel/concrt/lightweight-tasks.md)|В этом разделе описывается роль упрощенных задач.  Упрощенные задачи полезны при адаптации существующего кода к использованию функциональных возможностей планирования среды выполнения с параллелизмом.|  
|[Контексты](../../parallel/concrt/contexts.md)|В этом разделе описывается роль контекстов, функция `concurrency::wait` и класс `concurrency::Context`.  Используйте эту функциональность, если необходимо управлять блокированием, разблокированием и выдачей контекстов или если требуется разрешить превышение лимита в приложении.|  
|[Функции управления памятью](../Topic/Memory%20Management%20Functions.md)|В этом разделе описываются функции `concurrency::Alloc` и `concurrency::Free`.  Эти функции могут улучшить производительность памяти путем выделения и освобождения памяти в параллельном режиме.|  
|[Сравнение с другими моделями параллелизма](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|В этом разделе описываются различия между механизмами приоритетного планирования и координированного планирования.|  
|[Библиотека параллельных шаблонов](../../parallel/concrt/parallel-patterns-library-ppl.md)|В этом разделе описывается использование различных параллельных шаблонов, например параллельных алгоритмов, в ваших приложениях.|  
|[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)|В этом разделе описывается использование асинхронных агентов в ваших приложениях.|  
|[Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)|Описывает среду выполнения с параллелизмом, которая упрощает процесс параллельного программирования и содержит ссылки на соответствующие разделы.|