---
title: Открытие файлов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4abd2bf866a97e13324af22032cce9ebcaba4da
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408522"
---
# <a name="opening-files"></a>Открытие файлов

В MFC наиболее распространенный способ открытия файла — это двухэтапный процесс.

#### <a name="to-open-a-file"></a>Чтобы открыть файл

1. Создайте объект файла без указания пути или разрешение флаги.

     Обычно создается путем объявления объекта файла [CFile](../mfc/reference/cfile-class.md) переменной в кадре стека.

1. Вызовите [откройте](../mfc/reference/cfile-class.md#open) функция-член для объекта "файл", указав путь и разрешение флаги.

     Возвращаемое значение для `Open` ненулевое значение, если файл был успешно открыт, или 0, если не удалось открыть указанный файл. `Open` Функция-член является прототипом следующим образом:

     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

     Откройте флаги указать, какие разрешения, такие как только для чтения, необходимые для файла. Флаг возможные значения определяются как перечислимых констант в `CFile` класса, чтобы они были в определении "`CFile::`" в качестве `CFile::modeRead`. Используйте `CFile::modeCreate` флаг, если вы хотите создать файл.

Приведенный ниже показано, как создать новый файл с разрешениями чтения и записи (Замените любого предыдущего файла тот же путь):

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
>  В этом примере создает и открывает файл. При наличии проблем, `Open` возможности возврата вызова `CFileException` объекта в его последний параметр, как показано ниже. Макрос TRACE выводит имя и код, указывающий причину ошибки. Вы можете вызвать `AfxThrowFileException` работать, если требуется более подробные отчеты об ошибках.

## <a name="see-also"></a>См. также

[Класс CFile](../mfc/reference/cfile-class.md)<br/>
[CFile::Open](../mfc/reference/cfile-class.md#open)<br/>
[Файлы](../mfc/files-in-mfc.md)

