---
title: "Параметры приложения, ATL мастера проекта | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8514cce9dc2732d4a97ac51895e1ab28975fcfa3
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="application-settings-atl-project-wizard"></a>Параметры приложений, мастер проектов ATL
Используйте **параметры приложения** мастера проекта ATL для создания и добавления основных функций в новый проект ATL.  
  
## <a name="server-type"></a>Тип сервера  
 Выберите один из трех типов серверов:  
  
 **Библиотека динамической компоновки (DLL)**  
 Выберите для создания внутрипроцессного сервера.  
  
 **Исполняемый файл (EXE)**  
 Выберите, чтобы создать локальный сервер out of process. Этот параметр не позволяет поддержку MFC или COM + 1.0. Он не позволяет объединение кода прокси и заглушки.  
  
 **Службы (EXE)**  
 Выберите, чтобы создать приложение Windows, работающей в фоновом режиме при запуске Windows. Этот параметр не позволяет поддержку MFC или COM + 1.0 или не позволяет объединение кода прокси и заглушки.  
  
## <a name="additional-options"></a>Дополнительные параметры  
  
> [!NOTE]
>  Все дополнительные параметры доступны только для проектов DLL.  
  
 **Разрешить объединение кода заглушки/прокси-сервера**  
 Выберите **Разрешить объединение кода прокси и заглушки** флажок для удобства при необходимости маршалинг интерфейсов. Этот параметр помещает созданный MIDL код прокси и заглушки в том же исполняемый файл, что и сервер.  
  
 **Поддержка MFC**  
 Выберите, чтобы указать, что объект включает поддержку MFC. Этот параметр связывает проект с библиотеками MFC, таким образом, можно использовать все классы и функции, которые они содержат.  
  
 **Поддержка COM + 1.0**  
 Выберите, чтобы изменить параметры построения проекта для поддержки компонентов COM + 1.0. В дополнение к стандартному списку библиотек мастер добавляет comsvcs.lib библиотеку для компонента COM + 1.0  
  
 Кроме того mtxex.dll-delay, загружаемой на системе узла, при запуске приложения.  
  
-   **Поддержка регистрации компонента** Если проект ATL содержит поддержку компонентов COM + 1.0, можно задать этот параметр. Регистратор компонентов позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменять регистрацию компонентов (по отдельности или все сразу).  
  
## <a name="see-also"></a>См. также  
 [Мастер проекта ATL](../../atl/reference/atl-project-wizard.md)   
 [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)   
 [Конфигурации проекта ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

