---
title: "Практическое руководство. Извлечение времени, прошедшего с момента запуска Windows (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "счетчики, затраченное время"
  - "начальные"
  - "начальные, время, прошедшее с момента"
  - "счетчики тактов"
  - "время, время, прошедшее с момента запуска"
ms.assetid: a31fdecc-099e-4dd1-a176-f682289c5dd0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Извлечение времени, прошедшего с момента запуска Windows (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода показано, как определить счетчик тактов или число миллисекунд, прошедших с момента запуска Windows.  Данное значение хранится в свойстве <xref:System.Environment.TickCount%2A?displayProperty=fullName> и в связи с тем, что это значение является 32\-битным, оно обнуляется приблизительно каждые 24,9 дней.  
  
## Пример  
  
```  
// startup_time.cpp  
// compile with: /clr  
using namespace System;  
  
int main( )   
{  
   Int32 tc = Environment::TickCount;  
   Int32 seconds = tc / 1000;  
   Int32 minutes = seconds / 60;  
   float hours = static_cast<float>(minutes) / 60;  
   float days = hours / 24;  
  
   Console::WriteLine("Milliseconds since startup: {0}", tc);  
   Console::WriteLine("Seconds since startup: {0}", seconds);  
   Console::WriteLine("Minutes since startup: {0}", minutes);  
   Console::WriteLine("Hours since startup: {0}", hours);  
   Console::WriteLine("Days since startup: {0}", days);  
  
   return 0;  
}  
```  
  
## См. также  
 [Операции Windows](../dotnet/windows-operations-cpp-cli.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)