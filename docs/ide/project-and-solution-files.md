---
title: Файлы проектов и решений | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.files.projectandsolution
dev_langs:
- C++
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f52041ef8049e0e7ad4b12677ac1599b2cfd5669
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408197"
---
# <a name="project-and-solution-files"></a>Файлы проекта и решения

При создании проекта в Visual Studio создаются следующие файлы. Они используются для управлениями файлами проекта в решении.

|имя_файла|Расположение каталога|Расположение в обозревателе решений|Описание:|
|--------------|------------------------|--------------------------------|-----------------|
|*Имя_решения*.sln|*Имя_проекта*|Не отображается в обозревателе решений|Файл *решения*. Используется для организации всех элементов проекта или нескольких проектов в единое решение.|
|*Имя_проекта*.suo|*Имя_проекта*|Не отображается в обозревателе решений|Файл *параметров решения*. Сохраняет настройки решения, чтобы при любом открытии проекта или файла в решении оно выглядело и вело себя необходимым образом.|
|*Имя_проекта*.vcxproj|*Имя_проекта*|Не отображается в обозревателе решений|Файл *проекта*. Хранит информацию, относящуюся к каждому проекту. (В более ранних версиях этот файл назывался *Имя_проекта*.vcproj или *Имя_проекта*.dsp.) Пример файла проекта Visual C++ см. в разделе [Файлы проекта](../ide/project-files.md).|
|*Имя_проекта*.vcxitems|*Имя_проекта*|Не отображается в обозревателе решений|Файл *проекта общих элементов*. Этот проект не создается.  Вместо этого на него может сослаться другой проект C++, и его файлы станут частью процесса сборки ссылающегося проекта. Это можно использовать для совместного использования общего кода в кроссплатформенных проектах C++.|
|*Имя_проекта*.sdf|*Имя_проекта*|Не отображается в обозревателе решений|Файл *базы данных просмотра*. Поддерживает возможности просмотра и навигации, такие как **Перейти к определению**, **Найти все ссылки** и **Представление классов**. Создается путем анализа файлов заголовков.|
|*Имя_проекта.* vcxproj.filters|*Имя_проекта*|Не отображается в обозревателе решений|Файл *фильтров*. Указывает, куда поместить файл, который добавляется в решение. Например, H-файл помещается в узел **Файлы заголовков**.|
|*Имя_проекта.* vcxproj.user|*Имя_проекта*|Не отображается в обозревателе решений|Файл *пользователя миграции*. После миграции проекта из Visual Studio 2008 в этом файле появляются данные, преобразованные из любых VSPROPS-файлов.|
|*Имя_проекта*.idl|*Имя_проекта*|Исходный код|(Для конкретных проектов) Содержит исходный код на языке описания интерфейсов (IDL) для библиотеки типов элементов управления. Используется Visual C++ для создания библиотеки типов. Созданная библиотека предоставляет доступ к интерфейсу элемента управления другим клиентам автоматизации. Дополнительные сведения см. в разделе [Файл определения интерфейса (IDL-файл)](/windows/desktop/Rpc/the-interface-definition-language-idl-file) для пакета Windows SDK.|
|Readme.txt|*Имя_проекта*|Проект|Файл *сведений*. Создается мастером приложений и описывает файлы в проекте.|

## <a name="see-also"></a>См. также

[Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)