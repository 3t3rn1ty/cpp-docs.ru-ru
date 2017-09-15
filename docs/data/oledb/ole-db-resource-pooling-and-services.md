---
title: "Создание пулов ресурсов и служб OLE DB | Microsoft Docs"
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
  - "поставщики OLE DB, создание пулов ресурсов"
  - "службы OLE DB [OLE DB]"
  - "службы OLE DB [OLE DB], требования поставщика"
  - "OLE DB, создание пулов ресурсов"
  - "создание пулов ресурсов [OLE DB], требования поставщика"
  - "поставщики служб [OLE DB]"
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Создание пулов ресурсов и служб OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для работы с пулом или любыми другими службами OLE DB поставщик должен поддерживать агрегирование всех объектов.  Это требование предъявляется поставщиками OLE DB версии 1.5 или более поздней.  Если это требование не выполняется, использование служб невозможно.  Для поставщиков, не поддерживающих агрегирование, невозможно создание пула и использование дополнительных служб.  
  
 Создание пулов возможно только для поставщиков, поддерживающих свободную потоковую модель.  Потоковая модель поставщика определяется в пуле ресурсов в соответствии со значением свойства **DBPROP\_THREADMODEL**.  
  
 Если глобальное состояние поставщика может измениться, когда источник данных находится в инициализированном состоянии, поставщик должен поддерживать свойство **DBPROP\_RESETDATASOURCE**.  Это свойство вызывается перед повторным использованием подключения и позволяет очистить состояние поставщика перед его повторным использованием.  Если не удается очистить связанное с подключением состояние поставщика, для отмены повторного использования подключения можно возвратить значение **DBPROPSTATUS\_NOTSETTABLE** свойства.  
  
 Поставщики, в которых используется подключение к удаленной базе данных и предусматривается обнаружение возможности потери соединения, должны поддерживать свойство **DBPROP\_CONNECTIONSTATUS**.  C помощью этого свойства службы OLE DB могут обнаруживать неработающие подключения и обеспечивать их невозвращение в пул.  
  
 Наконец, автоматическое зачисление транзакций обычно работает только в том случае, если оно реализовано на том же уровне, что и создание пулов.  Поставщики, которые поддерживают автоматическое зачисление транзакций, должны поддерживать отключение зачисления с помощью свойства **DBPROP\_INIT\_OLEDBSERVICES**, а также при отмене выбора свойства **DBPROPVAL\_OS\_TXNENLISTMENT**.  
  
## См. также  
 [Дополнительные способы использования поставщика](../Topic/Advanced%20Provider%20Techniques.md)