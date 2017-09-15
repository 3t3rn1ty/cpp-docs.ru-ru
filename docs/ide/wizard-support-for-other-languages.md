---
title: "Поддержка мастера для других языков | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.EastAsianLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "поддержка языка для проектов MFC"
  - "проекты [C++], поддержка языка"
  - "мастера [C++], поддержка языка"
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Поддержка мастера для других языков
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При установке Visual Studio программа установки определят язык и региональные параметры системы и устанавливает соответствующий языковой шаблон или шаблоны.  Например, для западноевропейских региональных параметров программа установки устанавливает английский, французский, итальянский, испанский и немецкий языковые шаблоны.  Эти языки отражены в списке **Язык ресурсов** на странице [Тип приложения](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) мастера приложений MFC.  
  
## Языковые шаблоны  
 Не все шаблоны устанавливаются во всех системах, поскольку шаблоны основаны на кодировке ANSI, и не все ресурсы могут редактироваться во всех системах.  Например, по умолчанию невозможно редактировать ресурсы японского языка во французской системе.  
  
 Если используется ОС Windows 2000 или более поздняя версия и требуется создать приложение MFC на другом языке, необходимо скопировать в систему каталог шаблонов для соответствующего языка с установочного диска Visual Studio \(диск 1\).  
  
> [!NOTE]
>  Для редактирования созданного проекта необходимо установить соответствующие выбранному языку региональные параметры системы.  
  
 Каждому шаблону соответствует папка в каталоге \\Microsoft Visual Studio .NET 2003\\Vc7\\VCWizards\\mfcappwiz\\templates\\, согласно следующей таблице.  Чтобы получить доступ к нужному языковому шаблону, скопируйте соответствующую папку в каталог \\mfcappwiz\\templates\\ на компьютере.  После копирования папки в списке **Язык ресурсов** на странице **Тип приложения** в мастере приложений MFC появится выбранный язык.  
  
### Языковые шаблоны в Visual Studio .NET  
  
|Язык|Шаблон|  
|----------|------------|  
|Китайский \(традиционное письмо\)|1028|  
|Китайский \(упрощенный\)|2052|  
|Английский|1033|  
|Французский|1036|  
|Немецкий|1031|  
|Итальянский|1040|  
|Японский|1041|  
|Корейский|1042|  
|Испанский|3082|  
  
## Формат файлов, созданных мастером Visual C\+\+.  
 Если установленная языковая версия Visual Studio не совпадает с региональными параметрами системы, мастера Visual C\+\+ создают проекты в кодировке Юникод.  Например, если японская версия Visual Studio установлена на компьютере с региональными параметрами любого другого языка, мастера Visual C\+\+ будут создавать проекты, содержащие файлы в кодировке Юникод.  Это обычная практика для компьютеров, на которых установлены пакеты многоязыкового интерфейса пользователя Windows.  
  
 Такое поведение отличается от поведения систем, в которых региональные параметры соответствуют языковой версии Visual Studio.  В этом случае файлы проекта будут создаваться в кодировке ANSI, соответствующей кодовой странице системы.  
  
## См. также  
 [Типы файлов, создаваемых для проектов Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Создание проектов Visual C\+\+ и управление ими](../ide/creating-and-managing-visual-cpp-projects.md)