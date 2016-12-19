---
title: "Ошибка MSBuild MSB3151 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.IncludedProductIncluded"
helpviewer_keywords: 
  - "MSB3151"
ms.assetid: e4766734-2e90-436e-850b-a8a9da535dee
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Ошибка MSBuild MSB3151
**MSB3151: элемент "\<пакет\>" уже включает "\<пакет\>".**  
  
 Это предупреждение появляется, когда выбрано два пакета загрузчика, и один пакет включен в другой \(например, выбор включенного пакета является излишним\).  
  
### Чтобы исправить эту ошибку  
  
-   Снимите флажок для излишнего включенного пакета.