---
title: Советы по программированию многобайтовой Кодировки Общие | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc27d0b0396fed6e6b03f6c3f8e1f2332fcceecf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421106"
---
# <a name="general-mbcs-programming-advice"></a>Общие советы по программированию многобайтовой кодировки

Следуйте приведенным ниже советам:

- Для обеспечения гибкости, использовать макросы во время выполнения, например `_tcschr` и `_tcscpy` по возможности. Дополнительные сведения см. в разделе [универсальные текстовые сопоставления в файле Tchar.h](../text/generic-text-mappings-in-tchar-h.md).

- Использование времени выполнения C `_getmbcp` функцию, чтобы получить сведения о текущей кодовой странице.

- Не используйте повторно строковые ресурсы. В зависимости от целевого языка заданной строкой может иметь разные значения, при переводе. Например главное меню «Файл» в приложении может по-разному перевод из строки «Файл» в диалоговом окне. Если необходимо использовать более одной строки с одинаковым именем, используйте другую строку идентификаторы для каждого.

- Может потребоваться узнать, работает ли приложение на операционную систему с поддержкой многобайтовой Кодировки. Для этого нужно установите флаг при запуске программы; не следует полагаться на вызовы API.

- При разработке диалоговым окнам, разрешить примерно на 30% дополнительное пространство в конце статических текстовых элементов управления для перевода MBCS.

- Будьте внимательны при Выбор шрифтов для вашего приложения, так как некоторые шрифты доступны не во всех системах.

- При выборе шрифт для диалоговых окон, использовать [MS Shell Dlg](/windows/desktop/Intl/using-ms-shell-dlg-and-ms-shell-dlg-2) вместо MS Sans Serif или Helvetica. MS Shell Dlg заменяется нужный шрифт в системе перед созданием диалоговое окно. С помощью MS Shell Dlg гарантирует, что любые изменения в операционной системе для работы с данным шрифтом, автоматически становятся доступными. (MFC заменяет MS Shell Dlg DEFAULT_GUI_FONT или системного шрифта в Windows 95, Windows 98 и Windows NT 4, так как эти системы не обрабатывают MS Shell Dlg правильно.)

- При разработке приложения, решите, какие строки могут быть локализованы. В случае сомнений, предполагается, что все строки будет локализовано. Таким образом не следует смешивать строки, которые можно локализовать теми значениями, которые нельзя.

## <a name="see-also"></a>См. также

[Советы по программированию многобайтовой кодировки](../text/mbcs-programming-tips.md)<br/>
[Увеличение и уменьшение значений указателей](../text/incrementing-and-decrementing-pointers.md)