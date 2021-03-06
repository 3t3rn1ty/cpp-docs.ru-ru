---
title: -E (Предварительная обработка до stdout) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /e
dev_langs:
- C++
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48517f4469f203f5e29fbaa4ec105a3e36aafb44
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720275"
---
# <a name="e-preprocess-to-stdout"></a>/E (Предварительная обработка до stdout)

Выполняет предварительную обработку исходными файлами C и C++ и копирует предварительно обработанных файлов на стандартное устройство вывода.

## <a name="syntax"></a>Синтаксис

```
/E
```

## <a name="remarks"></a>Примечания

В этом процессе, выполняются все директивы препроцессора, расширения макросов и комментарии будут удалены. Чтобы сохранить комментарии в предварительно обработанные выходные данные, используйте [/C (сохранять комментарии во время предварительной обработки)](../../build/reference/c-preserve-comments-during-preprocessing.md) также параметр компилятора.

**/E** добавляет `#line` директивы в выходные данные в начале и конце каждого включенного файла, а также вокруг строк, удаленных директивами препроцессора для условной компиляции. Эти директивы перенумерации строки из предварительно обработанного файла. В результате ошибки, созданные в более поздних этапах обработки см. для номера строки исходного файла, а не строк предварительно обработанного файла.

**/E** параметр отменяет компиляцию. Отправьте предварительно обработанного файла для компиляции. **/E** также подавляются выходные файлы из **/FA**, **/Fa**, и **/Fm** параметры. Дополнительные сведения см. в разделе [/FA, /Fa (файл листинга)](../../build/reference/fa-fa-listing-file.md) и [/Fm (имя файла сопоставления)](../../build/reference/fm-name-mapfile.md).

Чтобы подавить `#line` использовать директивы, [/EP (Предварительная обработка в stdout без директив #line)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) вместо него.

Для отправки предварительно обработанные выходные данные в файл вместо `stdout`, использовать [/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md) вместо него.

Чтобы подавить `#line` директивы и отправки предварительно обработанные выходные данные в файл, используйте **/P** и **/EP** друг с другом.

Нельзя использовать предкомпилированные заголовки с **/E** параметр.

Обратите внимание на то, что при предварительной обработке в отдельном файле, пробелы не ставятся после маркеров. Это может привести к недопустимой программе или иметь нежелательные побочные эффекты. Следующая программа компилируется успешно:

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

Тем не менее если компиляция выполняется с помощью:

```
cl -E test.cpp > test2.cpp
```

`int main` в test2.cpp неправильно будет `intmain`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в **Дополнительные параметры**поле.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Пример

Следующая командная строка выполняет предварительную обработку `ADD.C`, сохраняет комментарии, добавляет `#line` директивы и выводит результат на стандартное устройство вывода:

```
CL /E /C ADD.C
```

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)