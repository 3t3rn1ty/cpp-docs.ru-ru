---
title: По умолчанию события элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 95c3d15414dbb312c60029a86707c1d32df56adc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405519"
---
# <a name="default-control-events"></a>События по умолчанию элемента управления

Следующие имена элементов управления имеют соответствующие им события:

|Имя элемента управления|Событие по умолчанию|
|------------------|-------------------|
|Анимация|ACN_START|
|Флажок|BN_CLICKED|
|Поле со списком|CBN_SELCHANGE|
|Другой|TTN_GETDISPINFO|
|Выбор даты / времени|DTN_DATETIMECHANGE|
|Поле ввода|СОБЫТИЕ EN_CHANGE|
|Область группы|(Неприменимо)|
|Сочетания клавиш|NM_OUTOFMEMORY|
|IP-адрес|IPN_FIELDCHANGED|
|Список|LVN_ITEMCHANGE|
|Список|LBN_SELCHANGE|
|Календарь месяца|MCN_SELCHANGE|
|Управления изображения|(Неприменимо)|
|Ход выполнения|NM_CUSTOMDRAW|
|Кнопка|BN_CLICKED|
|Переключатель|BN_CLICKED|
|"Rich edit"|СОБЫТИЕ EN_CHANGE|
|Полоса прокрутки|NM_THEMECHANGED|
|Slider|NM_CUSTOMDRAW|
|"Счетчик"|UDN_DELTAPOS|
|Статический текст|(Неприменимо)|
|Tab|TCN_SELCHANGE|
|Дерево|TVN_SELCHANGE|

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Определение переменных-членов для элементов управления диалоговых окон](../windows/defining-member-variables-for-dialog-controls.md)<br/>
[Типы сообщений, связанных с объектами пользовательского интерфейса](../mfc/reference/message-types-associated-with-user-interface-objects.md)<br/>
[Редактирование обработчика сообщений](../mfc/reference/editing-a-message-handler.md)<br/>
[Определение обработчика сообщений для отраженного сообщения](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)<br/>
[Объявление переменной на основании нового класса элемента управления](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)<br/>
[Переопределение виртуальной функции](../ide/overriding-a-virtual-function-visual-cpp.md)