---
title: '&lt;fstream&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <fstream>
dev_langs:
- C++
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b716248c6fe9d0734cd580800c9254cf01f2a17
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962878"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Определяет несколько классов, поддерживающих операции iostreams для последовательностей, хранящихся во внешних файлах.

## <a name="syntax"></a>Синтаксис

```cpp
#include <fstream>

```

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание:|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Тип `basic_filebuf` специализированный на **char** параметров шаблона.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Тип `basic_fstream` специализированный на **char** параметров шаблона.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Тип `basic_ifstream` специализированный на **char** параметров шаблона.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Тип `basic_ofstream` специализированный на **char** параметров шаблона.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Тип `basic_fstream` специализированный на **wchar_t** параметров шаблона.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Тип `basic_ifstream` специализированный на **wchar_t** параметров шаблона.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Тип `basic_ofstream` специализированный на **wchar_t** параметров шаблона.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Тип `basic_filebuf` специализированный на **wchar_t** параметров шаблона.|

### <a name="classes"></a>Классы

|Класс|Описание:|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Класс шаблона описывает буфер потока, который управляет передачей элементов типа `Elem`, признаки символов которого определяются с помощью класса `Tr`, в последовательность элементов, сохраненную во внешнем файле, и из нее.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Класс шаблона описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**,  **TR**>, с элементами типа `Elem`, признаки символов определяются классом `Tr`.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Класс шаблона описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, с элементами типа `Elem`, признаки символов определяются классом `Tr`.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Этот класс шаблона описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, с элементами типа `Elem`, признаки символов определяются классом `Tr`.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
