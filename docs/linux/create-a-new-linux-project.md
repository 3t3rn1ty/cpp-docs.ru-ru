---
title: Создание нового проекта C++ Linux в Visual Studio | Документы Майкрософт
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 2386d89afcd566dac77f62cd0afc36e5952674ab
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601422"
---
# <a name="create-a-new-linux-project"></a>Создание нового проекта Linux

Сначала убедитесь, что вы установили **рабочую нагрузку разработки для Linux** в Visual Studio. См. дополнительные сведения о [скачивании, установке и настройке рабочей нагрузки для Linux](download-install-and-setup-the-linux-development-workload.md).

При написании кода на C++ в Visual Studio для Linux можно выбрать создаваемый проект: проект Visual Studio или проект CMake. В этом разделе описывается создание проекта Visual Studio. Сведения о проектах CMake см. в разделе [Настройка проекта CMake Linux](cmake-linux-project.md).

Чтобы создать новый проект Linux в Visual Studio, выполните следующие действия.

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Выберите узел **Visual C++ > Кроссплатформенный > Linux**, затем выберите тип проекта, который вы хотите создать, введите имя и расположение и нажмите кнопку "ОК".

   ![Новый проект Linux](media/newproject.png)

   | Тип проекта | Описание:
   | ------------ | ---
   | **Blink (Raspberry)**           | Проект, предназначенный для устройства Raspberry Pi, с образцом кода, написанным для мерцания светодиодного индикатора
   | **Консольное приложение (Linux)** | Проект, предназначенный для любого компьютера Linux, с образцом кода, написанным для вывода текста на консоль
   | **Пустой проект (Linux)**       | Проект, предназначенный для любого компьютера Linux, без образца кода
   | **Проект Makefile (Linux)**    | Проект, предназначенный для любого компьютера Linux, который будет собран с использованием стандартной системы сборки Makefile

