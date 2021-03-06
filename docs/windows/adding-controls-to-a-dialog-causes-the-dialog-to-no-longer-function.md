---
title: Добавление элементов управления в диалоговое окно приводит к прекращению работы (C++) диалогового окна | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89e4a639ad953593195401fe2eadeb5d7877a160
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445871"
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function-c"></a>Добавление элементов управления в диалоговое окно приводит к прекращению работы (C++) диалогового окна

После добавления общего элемента управления или элемента управления форматированным редактированием в диалоговое окно, она не будет отображаться при тестировании диалогового или самого диалогового окна не будет отображаться.

### <a name="example-of-the-problem"></a>Пример проблемы

1. Создайте проект Win32, измените параметры приложения, поэтому создается приложение Windows (не консольное приложение).

2. В [представление ресурсов](../windows/resource-view-window.md), дважды щелкните RC-файл.

3. В группе параметров диалогового окна щелкните **о** поле.

4. Добавить **контроль IP-адресов** в диалоговое окно.

5. Сохранить и **перестроить все**.

6. Запустите программу.

7. В диалоговом окне **помочь** меню, щелкните **о** командной; диалоговое окно не появляется.

### <a name="the-cause"></a>Причины

В настоящее время редактора диалоговых окон не добавляет автоматически код в проект при перетаскивании следующие общие элементы управления или элементов управления в диалоговое окно "rich edit". И не Visual Studio обеспечивает ошибку или предупреждение при возникновении этой проблемы. Необходимо вручную добавить код для элемента управления.

||||
|-|-|-|
|Элемент управления «Ползунок»|Дерево|Элемент управления "Выбор даты и времени"|
|Элемент управления "Счетчик"|Набор вкладок|Календарь месяца|
|Элемент управления хода выполнения|Анимация элемента управления|Контроль IP-адресов|
|Сочетания клавиш|Элемент управления "Rich Edit"|Расширенное поле со списком поле|
|Управления "список"|Элемент управления Rich Edit 2.0|Пользовательский элемент управления|

## <a name="the-fix-for-common-controls"></a>Исправление для стандартных элементов управления

Чтобы использовать стандартные элементы управления в диалоговом окне, необходимо вызвать [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) или `AFXInitCommonControls` перед созданием диалоговое окно.

## <a name="the-fix-for-richedit-controls"></a>Исправление для элементов управления RichEdit

Необходимо вызвать метод `LoadLibrary` для элементов управления "rich edit". Дополнительные сведения см. в разделе [использование элемента управления RichEdit 1.0 с MFC](../windows/using-the-richedit-1-0-control-with-mfc.md), [о элементами управления Rich Edit](/windows/desktop/Controls/about-rich-edit-controls) в пакете Windows SDK, и [Обзор элемента управления Rich Edit](../mfc/overview-of-the-rich-edit-control.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Устранение неполадок редактора диалоговых окон](../windows/troubleshooting-the-dialog-editor.md)<br/>
[Редактор диалоговых окон](../windows/dialog-editor.md)