---
title: "getcwd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getcwd"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "getcwd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "getcwd - функция"
ms.assetid: c740ab06-9ba0-4036-a025-ce3acded3ffe
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# getcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не рекомендуется использовать эту функцию POSIX.  Вместо неё используйте соответствующую стандарту ISO C\+\+ функцию [\_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).