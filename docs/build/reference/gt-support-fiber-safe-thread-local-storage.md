---
title: -GT (поддержка волокон Thread-Local памяти) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
dev_langs:
- C++
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eeec9ddce36777fc6fcb15b30a864f1c04a7b09b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700846"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (поддержка локальной памяти потока, безопасной относительно волокон)

Поддерживает безопасность волокон для данных, размещаемых с помощью статических локальной памяти потока, то есть данных, размещаемых с `__declspec(thread)`.

## <a name="syntax"></a>Синтаксис

```
/GT
```

## <a name="remarks"></a>Примечания

Данные объявлен с `__declspec(thread)` осуществляется с помощью массива локальное хранилище потока (TLS). Массив TLS представляет собой массив адресов, которые система хранит для каждого потока. Каждый адрес в этом массиве указывает расположение локальной памяти потока данных.

Волокно представляет упрощенный объект, который состоит из стека и контекста регистров и могут быть назначены на различные потоки. Волокно можно запустить в любом потоке. Так как волокно может быть выведено из и перезапустить позже в другом потоке, адрес массива TLS не должен кэшируемых или оптимизируемых как общее подвыражение во время вызова функции (см. в разделе [/Og (виды глобальной оптимизации)](../../build/reference/og-global-optimizations.md) для параметра сведения о). **/GT** предотвращает такую оптимизацию.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **оптимизации** страницу свойств.

1. Изменить **включить безопасную относительно волокон оптимизацию** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)