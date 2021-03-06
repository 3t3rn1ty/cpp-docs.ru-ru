---
title: Свойства команды меню (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c846cecb415365db92e3097bbf04ab06cd4209d0
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860450"
---
# <a name="menu-command-properties-c"></a>Свойства команды меню (C++)

Приведенные ниже сведения организованные в соответствии со **меню** свойства, которые отображаются в [окно "Свойства"](/visualstudio/ide/reference/properties-window) при выборе команды меню. Они перечислены в алфавитном порядке несмотря на то что **свойства** окно также позволяет просматривать эти свойства по категориям.

|Свойство.|Описание:|
|--------------|-----------------|
|**Break**|Допустимо одно из следующих значений.<br /><br />- **Нет** (по умолчанию): без разрыва.<br />- **Столбец**: для статических меню, это значение помещает команду меню в новой строке. В контекстных меню при этом значении команда меню помещается в новый столбец без разделительной линии между столбцами. Установка этого свойства влияет на внешний вид меню только во время выполнения. В редакторе внешний вид меню не меняется.<br />- **Панель**: совпадение с кодом **столбец** за исключением контекстных меню, это значение новый столбец отделяется от старого вертикальной линией. Задание этого свойства влияет на внешний вид меню только во время выполнения, не в **меню** редактора.|
|**Подпись**|Текст, представляющий команду меню (имя меню). Чтобы указать одну из букв названия команды меню как входящую в сочетание клавиш, поместите перед ней знак амперсанда (&).|
|**Помечено**|Если **True**, команда меню изначально установлен. Тип: **Bool**. Значение по умолчанию — **False**.|
|**Включено**|Если задано значение **False**, пункт меню отключен.|
|**Grayed (Серым цветом)**|Если **True**, команда меню изначально выделена серым цветом и неактивной. Тип: **Bool**. Значение по умолчанию — **False**.|
|**Справка**|Выравнивает пункт меню по правому краю. Например, команда меню **Справка** всегда находится справа во всех приложениях Windows. Если задано это свойство пункта меню, данный пункт будет отображаться прижатым к правому краю и в самом конце меню. Применяется к элементам верхнего уровня. Значение по умолчанию — **False**.|
|**Идентификатор**|Этот символ определяется в файле заголовка. Тип: **символ**, **целое число**, или **строка в кавычках**. Можно использовать любой символ, который обычно доступен в любом редакторе, даже если [окно свойств](/visualstudio/ide/reference/properties-window) не содержит раскрывающийся список для выбора этого символа.|
|**Контекстное меню**|Если **True**, команда меню является всплывающим меню. Тип: **Bool**. Значение по умолчанию — **True** для меню верхнего уровня в меню панели; в противном случае **False**.|
|**Запрашивать**|Содержит текст, отображаемый в строке состояния, при выделении этой команды меню. Текст помещается в таблицу строк с тем же идентификатором, что и команда меню. Это свойство доступно для любого типа проекта, но во время выполнения проявляются особенности, зависящие от MFC.|
|**Right to Left Justify (Выравнивание справа налево)**|Выравнивание команды меню по правому краю в строке меню во время выполнения. Тип: **Bool**. Значение по умолчанию — **False**.|
|**Right to Left Order (Справа налево)**|Отображение команд меню справа налево в тех случаях, когда интерфейс локализован для языка с направлением чтения справа налево, например, иврита или арабского языка.|
|**Separator**|Если **True**, команда меню является разделителем. Тип: **Bool**. Значение по умолчанию — **False**.|

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор меню](../windows/menu-editor.md)