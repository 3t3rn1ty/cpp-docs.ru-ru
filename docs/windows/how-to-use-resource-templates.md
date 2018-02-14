---
title: "Как: использование шаблонов ресурсов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- language-specific template files
- resource templates
- resources [Visual Studio], creating
- rct files
- templates, resource templates
- resources [Visual Studio], templates
- .rct files
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bace4f6d8835d9aece7679fa1bb89af3d7a20ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-resource-templates"></a>Практическое руководство. Использование шаблонов ресурсов
Шаблон ресурса — это настроенный ресурс, сохраненный как RCT-файл. Шаблон ресурса можно использовать в качестве отправной точки для создания других ресурсов. Шаблоны ресурсов позволяют сэкономить время при разработке дополнительных ресурсов или групп ресурсов, которые совместно используют какие-либо возможности, например, стандартные элементы управления и другие повторяющиеся элементы. Например, вы хотите поместить кнопку "Справка" и значок с логотипом компании в несколько диалоговых окон. Чтобы быстро сделать это, создайте новый шаблон диалогового окна и поместите в него логотип и кнопку "Справка".  
  
 После настройки шаблона ресурсов, необходимо сохранить изменения в папке шаблонов (или любом месте, указанном в пути включаемых файлов), чтобы новый шаблон ресурсов появился в своем разделе ресурса типа в [диалоговое окно "Добавить ресурс"](../windows/add-resource-dialog-box.md). После этого можно использовать новый шаблон ресурсов сколько угодно раз.  
  
> [!NOTE]
>  Файлы шаблонов, предназначенные для конкретных языков, можно разместить в подкаталогах основного каталога шаблонов. Например, можно поместить файлы англоязычных шаблонов в \\< каталог_шаблонов_ресурсов\>\1033.  
  
### <a name="to-create-a-template-for-resources"></a>Создание шаблонов ресурсов  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши проект.  
  
2.  В контекстном меню выберите **добавить**, нажмите кнопку **Добавление нового элемента**.  
  
3.  В **Добавление нового элемента** диалогового **шаблоны:** области, выберите **файл шаблона ресурсов (.rct)**.  
  
4.  Укажите имя и расположение нового RCT-файла и нажмите кнопку **откройте**.  
  
5.  Новый RCT-файл добавляется в проект и отображается в обозревателе решений в **ресурсов** папки.  
  
     Теперь можно дважды щелкнуть RCT-файл, чтобы открыть его в окне документа, а затем добавить в него ресурсы (щелкните правой кнопкой мыши файл в окне документа и выбрать **добавить ресурс** из контекстного меню). Затем можно настроить эти ресурсы и сохранить RCT-файл.  
  
    > [!NOTE]
    >  При создании нового RCT-файл Visual Studio ищет его в Visual Studio 9.0\VC\VCResourceTemplates \Program Files\Microsoft, в Visual Studio 9.0\VC\VCResourceTemplates \Program Files\Microsoft\\*LCID* () например 1033 для английского языка) *или* в любом месте [путь включения](../windows/how-to-specify-include-directories-for-resources.md). Если вы предпочитаете хранить RCT-файлы в другой папке, например, "\Мои документы", достаточно добавить эту папку в путь поиска включаемых файлов и Visual Studio найдет ваш RCT-файл.  
  
### <a name="to-convert-an-existing-rc-file-to-an-rct-file"></a>Преобразование существующего RC-файла в RCT-файл  
  
1.  [Откройте RC-файл как отдельный файл](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
2.  На **файл** меню, нажмите кнопку  **Сохранить \<* имя_файла*> как **.  
  
3.  Укажите расположение и нажмите кнопку **ОК**.  
  
### <a name="to-create-a-new-resource-from-a-template"></a>Создание нового ресурса по шаблону  
  
1.  В [представление ресурсов](../windows/resource-view-window.md) области, щелкните правой кнопкой мыши RC-файл и выберите **добавить ресурс** из контекстного меню.  
  
2.  В **добавить ресурс** диалогового окна щелкните знак «плюс» (**+**) рядом с ресурсом, чтобы развернуть узел ресурса и просмотреть все шаблоны, доступные для этого ресурса.  
  
3.  Дважды щелкните шаблон, который нужно использовать.  
  
4.  При необходимости измените добавленный ресурс в редакторе ресурсов.  
  
     Редактор ресурсов автоматически предоставляет уникальный идентификатор ресурса. Можно просмотреть и изменить [свойства ресурса](../windows/changing-the-properties-of-a-resource.md) при необходимости.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.*  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)