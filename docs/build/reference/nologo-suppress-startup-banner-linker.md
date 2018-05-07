---
title: -NOLOGO (отключение начального заголовка) (компоновщик) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
dev_langs:
- C++
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a76e99496114c0ebdc60f81724e67dd88a482055
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (отмена вывода начального заголовка) (Компоновщик)
```  
/NOLOGO  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/nologo не отображать об авторских правах и номере версии.  
  
 Этот параметр также отключает вывод из командных файлов. Дополнительные сведения см. в разделе [командные файлы LINK](../../build/reference/link-command-files.md).  
  
 По умолчанию эти сведения будут отправлены компоновщиком в окно вывода. В командной строке он отправляется в стандартный вывод и могут быть перенаправлены в файл.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Этот параметр должен использоваться только из командной строки.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  Данного параметра компоновщика программным способом нельзя.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)