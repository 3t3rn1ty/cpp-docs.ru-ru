---
title: "Включение и отключение служб поставщика | Microsoft Docs"
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
  - "службы OLE DB [OLE DB], включение и отключение"
  - "поставщики служб [OLE DB]"
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Включение и отключение служб поставщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

По умолчанию отдельные службы OLE DB можно включить или отключить для всех приложений, в которых используется один поставщик.  Для этого необходимо добавить в раздел CLSID поставщика запись реестра **OLEDB\_SERVICES**, содержащую значение типа `DWORD`, которое определяет включение или отключение службы, как показано в следующей таблице.  
  
|Включенные по умолчанию службы|Значение ключевого слова|  
|------------------------------------|------------------------------|  
|Все службы \(по умолчанию\)|0xffffffff|  
|Все, за исключением служб заполнения и автоматического зачисления|0xfffffffe|  
|Все, за исключением службы клиентских курсоров|0xfffffffb|  
|Все, за исключением служб регулирования количества запросов, автоматического зачисления и клиентских курсоров|0xfffffff0|  
|Все службы отключены|0x00000000|  
|Агрегирование не выполняется, все службы отключены|\<missing key\>|  
  
## См. также  
 [Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)