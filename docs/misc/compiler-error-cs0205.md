---
title: "Ошибка компилятора CS0205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0205"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0205"
ms.assetid: 616d98cf-e7a5-4f8e-93da-fcd6e1e4de35
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS0205
Не удается вызвать абстрактный член базового класса: "метод"  
  
 Вы не можете вызвать [абстрактный](../Topic/abstract%20\(C%23%20Reference\).md) метод, так как он не имеет тела метода. Для получения дополнительной информации см. [Абстрактные и запечатанные классы и члены классов](../Topic/Abstract%20and%20Sealed%20Classes%20and%20Class%20Members%20\(C%23%20Programming%20Guide\).md).  
  
 В следующем примере возникает ошибка CS0205.  
  
```  
// CS0205.cs abstract public class MyClass { abstract public void M(); } public class MyClass2 : MyClass { public override void M() { base.M();   // CS0205, delete this line } public static void Main() { } }  
```