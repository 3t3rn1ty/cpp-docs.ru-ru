---
title: "Структура WSADATA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WSADATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WSADATA - структура"
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Структура WSADATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `WSADATA` используется по умолчанию для инициализации сокетов витрин, возвращенные вызовом глобальной функции `AfxSocketInit`.  
  
## Синтаксис  
  
```  
  
      struct WSAData {  
   WORD wVersion;  
   WORD wHighVersion;  
   char szDescription[WSADESCRIPTION_LEN+1];  
   char szSystemStatus[WSASYSSTATUS_LEN+1];  
   unsigned short iMaxSockets;  
   unsigned short iMaxUdpDg;  
   char FAR * lpVendorInfo;  
};  
```  
  
#### Параметры  
 *wVersion*  
 Версия спецификации Windows SSL, что библиотека DLL Windows SSL требуется вызывающий объект для использования.  
  
 *wHighVersion*  
 Самая высокая версия спецификации Windows SSL, эта библиотека DLL может поддерживать \(также кодировкой как выше\).  Обычно это значение совпадает с **wVersion**.  
  
 *szDescription*  
 Объединения завершенной строка ASCII, в которую DLL Windows sockets копирует описание реализации SSL Windows, включая идентификацию поставщика.  Текст \(до 256 символов в длину\) может содержать любые символы, но предостережен поставщики для включения элемента управления и символы форматирования. наиболее правоподобное использовать, что приложение заключит это для отображения \(по возможности усечения\) в сообщении о состоянии.  
  
 *szSystemStatus*  
 Объединения завершенной строка ASCII, в которую DLL Windows sockets копирует соответствующих состояние или сведения о конфигурации.  Библиотека DLL Windows SSL, необходимо использовать это поле, только если сведения могут быть полезны пользователю или вспомогательному персоналу; он не должен быть рассмотрен как расширение поля **szDescription**.  
  
 *iMaxSockets*  
 Максимальное количество сокетов, один процесс потенциально может открыть.  Реализация SSL Windows может предоставить глобального пула сокетов для выделения в любой процесс; кроме того, она позволяет выделять ресурсы для каждого процесса для сокетов.  Число может отражать хорошо способ, которым была установлена библиотека DLL Windows SSL или сетевого программного обеспечения.  Модули записи приложения могут использовать это значение в качестве незрелая ситуация ли реализация Windows sockets использующихся приложением.  Например, сервер Windows x может проверить **iMaxSockets** при первом содержит: если он меньше 8, то приложение отобразит сообщение об ошибке инструктируя пользователь перенастройки сетевое программное обеспечение. \(Это ситуация, в которой текст **szSystemStatus** может использоваться\). Очевидно, что невозможно задать определенное приложение могло фактически выбор сокеты **iMaxSockets**, поскольку могут быть другие приложения Windows SSL в использовании.  
  
 *iMaxUdpDg*  
 Размер в байтах самой крупной датаграммы UDP \(UDP\), которая может быть отправлена или выполняется приложением Windows SSL.  Если реализация не накладывает ограничение не задано, то значение **iMaxUdpDg** равно нулю.  Во многих реализаций сокетов Беркли, существует ограничение в 8192 байт датаграммах UDP, делятся \(при необходимости\).  Реализация SSL Windows может наложить ограничение на основе, например в выделении буферов разборки фрагмента.  Минимальное значение **iMaxUdpDg** для реализации совместимой sockets Windows 512.  Обратите внимание, что вне зависимости от значения **iMaxUdpDg**, пытаться нецелесообразно отправлять широковещательная датаграмма, больше MTU \(MTU\) для сети. API Windows \(SSL не предоставляет механизм для обнаружения MTU, но он должен быть не меньше 512 байт\).  
  
 *lpVendorInfo*  
 Далекий указатель на структуру данных, связанных с поставщиком.  Определение этой структуры \(если указан\), выходящей за область спецификации Windows SSL.  
  
> [!NOTE]
>  В MFC структура `WSADATA` возвращается функцией `AfxSocketInit`, которая вызывается в функции `InitInstance`.  Можно получить структуру и сохраняет его в программе, если необходимо использовать сведения из их позже.  
  
## Требования  
 **Заголовок:** winsock2.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../Topic/AfxSocketInit.md)