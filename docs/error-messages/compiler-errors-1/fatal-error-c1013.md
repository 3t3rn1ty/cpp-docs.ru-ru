---
title: "Неустранимая ошибка C1013 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1013
dev_langs:
- C++
helpviewer_keywords:
- C1013
ms.assetid: 5514a679-efe7-4055-bdd3-5693ca0c332f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bdc830c526c7093dcc1219df22a41a096aeaf9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1013"></a>Неустранимая ошибка C1013
ограничение компилятора: слишком много открывающих круглых скобок  
  
 Выражение содержит слишком много уровней круглых скобок в одном выражении. Упростите выражение или разбейте его на несколько инструкций.  
  
 До Visual C++ 6.0 с пакетом обновления 3 в одном выражении могло быть не более 59 вложенных круглых скобок. В настоящее время ограничение на количество круглых скобок увеличено до 256.