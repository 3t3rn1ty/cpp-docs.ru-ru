---
title: Перемещение строки из одного файла ресурса в другой (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d8ebfc8f1111049368a76a9b153fcf8079a4edd
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081862"
---
# <a name="moving-a-string-from-one-resource-file-to-another-c"></a>Перемещение строки из одного файла ресурса в другой (C++)

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Перемещение строки из одного файла скрипта ресурсов в другую

1. Откройте таблицы строк в обоих RC-файлов. (Дополнительные сведения см. в разделе [Просмотр ресурсов в файл скрипта ресурсов за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Щелкните правой кнопкой мыши строку, в которой нужно переместить и выберите **Вырезать** в контекстном меню.

3. Поместите курсор в целевом объекте **редактор строк** окна.

4. В RC-файле, к которому нужно вставить строку, щелкните правой кнопкой мыши и выберите **вставить** в контекстном меню.

   > [!NOTE]
   > Если **идентификатор** или **значение** перемещенной строки конфликтует с существующим **идентификатор** или **значение** в целевом файле, либо **Идентификатор** или **значение** перемещенной строки изменений. Если строка существует с тем же **идентификатор**, **идентификатор** перемещенной строки изменений. Если строка существует с тем же **значение**, **значение** перемещенной строки изменений.

Сведения о добавлении ресурсов в управляемые проекты (предназначенные среда CLR), см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор строк](../windows/string-editor.md)<br/>
[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Настройка макетов окон](/visualstudio/ide/customizing-window-layouts-in-visual-studio)  