---
title: "Ошибка компилятора C3391 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3391"
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"аргумент\_типа": недопустимый аргумент типа для универсального параметра "параметр" универсального типа "универсальный\_тип"; должен быть тип значения, не допускающий значения null  
  
 Экземпляр универсального типа был создан неправильно.  Проверьте определение типа.  Дополнительные сведения см. в разделах <xref:System.Nullable> и [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере на языке C\# создается компонент, содержащий универсальный тип, который имеет определенные ограничения, не поддерживаемые при создании универсальных типов в [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)]. Дополнительные сведения см. в разделе [Ограничения параметров типа](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
```  
// C3391.cs // compile with: /target:library // a C# program public class GR<N> where N : struct {}  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3391:  
  
```  
// C3391_b.cpp // compile with: /clr #using <C3391.dll> using namespace System; value class VClass {}; int main() { GR< Nullable<VClass> >^ a = gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable GR<VClass>^ aa = gcnew GR<VClass>();   // OK }  
```