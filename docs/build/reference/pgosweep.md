---
title: "pgosweep | Microsoft Docs"
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
  - "pgosweep - программа"
  - "профильная оптимизация, pgosweep"
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# pgosweep
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется в профильной оптимизации для записи всех данных профиля из выполняющейся программы в файл PGC.  
  
## Синтаксис  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### Параметры  
 `options`  
 Дополнительный параметр, который можно не задавать.  Допустимыми значениями для `options` являются:  
  
-   **\/?** или **\/help,**  отображают справку.  
  
-   **\/noreset,** ведет счет в структурах данных времени выполнения.  
  
 `image`  
 Полный путь к файлу EXE или DLL, созданному с помощью параметра компилятора \/LTCG:PGINSTRUMENT.  
  
 `pgcfile`  
 Файл PGC, в который эта команда будет выписывать счетчики данных.  
  
## Заметки  
 Данная команда используется применительно к программам, построенным с помощью параметра компилятора \/LTCG:PGINSTRUMENT.  Она прерывает выполняющуюся программу и записывает данные профиля в новый файл PGC.  По умолчанию команда обнуляет счетчики после каждой операции записи.  Если задать параметр **\/noreset**, команда запишет значения, но не переустановит их в выполняющейся программе.  Этот параметр предоставит дубликат данных при последующем извлечении данных профиля.  
  
 Еще одним вариантом использования `pgosweep` является извлечение сведений о профиле, относящихся только ко времени выполнения приложения.  Например, можно запустить `pgosweep` сразу после запуска приложения и не использовать этот файл.  Это приведет к удалению данных профиля, связанных с издержками при запуске.  Затем можно выполнить `pgosweep` перед завершением приложения.  Теперь собранные данные включают сведения о профиле только во время выполнения.  
  
 При присваивании pgc\-файл \(`pgcfile`\) можно использовать стандартный формат, который *appname\!n*.pgc.  При использовании этого формата компилятор обнаружит данные на стадии \/LTCG:PGO.  Если стандартный формат не используется, необходимо использовать [pgomgr](../../build/reference/pgomgr.md) для слияния файлов PGC.  
  
## Пример  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 В данном примере `pgosweep` записывает текущую информацию о профиле для файла Myapp.exe в файл Myapp\!1.pgc.  
  
## См. также  
 [Средства профильной оптимизации](../../build/reference/tools-for-manual-profile-guided-optimization.md)