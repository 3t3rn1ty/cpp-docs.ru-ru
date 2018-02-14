---
title: "TN071: Реализация IOleCommandTarget в MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IOleCommandTarget
dev_langs: C++
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43f97774036c42fa0f681a65e0a335f944daf09c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: Реализация IOleCommandTarget в MFC
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 `IOleCommandTarget` Интерфейс включает объекты и их контейнеры для отправки команд друг с другом. Например, в панели инструментов объекта может содержать кнопки для команд **печати**, **предварительного просмотра перед печатью**, **Сохранить**, `New`, и **масштаба**. Если такого объекта были внедрены в контейнер, который поддерживает `IOleCommandTarget`, объект может включить ее кнопок и пересылки команды обработки, когда пользователь щелкнул их к контейнеру. Если контейнер для печати сам внедренного объекта, его выполнения данного запроса, отправив команду через `IOleCommandTarget` интерфейс внедренного объекта.  
  
 `IOleCommandTarget`Представляет интерфейс автоматизации, в котором используется клиентом для вызова методов на сервере. Однако использование `IOleCommandTarget` обеспечивает экономию ресурсов из вызовов, через интерфейсы автоматизации, так как программистам нет необходимости в использовании обычно дорогих `Invoke` метод `IDispatch`.  
  
 В MFC `IOleCommandTarget` интерфейс используется активный документ серверами позволяет контейнеры активных документов для отправки команд на сервер. Класс сервера активных документов `CDocObjectServerItem`, использует схемы интерфейсов MFC (см. [TN038: реализация MFC/OLE IUnknown](../mfc/tn038-mfc-ole-iunknown-implementation.md)) для реализации `IOleCommandTarget` интерфейса.  
  
 `IOleCommandTarget`также реализована в **COleFrameHook** класса. **COleFrameHook** недокументированные класса MFC, который реализует функциональные возможности окна фрейма на месте изменяет контейнеров. **COleFrameHook** также использует схемы интерфейсов MFC для реализации `IOleCommandTarget` интерфейса. **COleFrameHook**реализация `IOleCommandTarget` перенаправляет команды OLE для `COleDocObjectItem`-производный контейнеры активных документов. Это позволяет любой MFC активного документа контейнера, для получения сообщений от серверов автономной активного документа.  
  
## <a name="mfc-ole-command-maps"></a>Схемы команд OLE MFC  
 MFC-разработчики могут воспользоваться преимуществами `IOleCommandTarget` с помощью MFC OLE команды карты. Схемы команд OLE подобны схемы сообщений, так как они могут использоваться для сопоставления с функциями-членами класса, содержащего карты команд команды OLE. Чтобы добиться этого, поместите макросы в карты команд для указания команды, которые требуется обработать, команды OLE и идентификатор группы команд OLE [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение, которое будет отправляться при получении команды OLE. MFC также предоставляет ряд предопределенных макросов для стандартных команд OLE. Список стандартных OLE команды, которые изначально были разработаны для использования с приложениями Microsoft Office см. в разделе OLECMDID перечисления, который определен в docobj.h.  
  
 При получении приложением MFC, который содержит схему команды OLE команду OLE MFC пытается найти идентификатор команды и группы команд для запрашиваемую команду на карте команды OLE приложения. Если соответствие найдено, **WM_COMMAND** приложения, содержащего карты команд с Идентификатором запрашиваемую команду отправки сообщения. (См. в описании `ON_OLECMD` ниже.) Таким образом, команды OLE, отправляется в приложение, преобразуются в **WM_COMMAND** сообщения по MFC. **WM_COMMAND** сообщения затем направляются через схемы сообщений приложения с использованием стандарта MFC [маршрутизация команд](../mfc/command-routing.md) архитектуры.  
  
 В отличие от схемы сообщений MFC OLE команды карты не поддерживается ClassWizard. Разработчики MFC необходимо добавить поддержку карты команды OLE и записи карты команд OLE вручную. OLE схемы команд можно добавить MFC активных серверов документ в любом классе, который находится в **WM_COMMAND** цепочки маршрутизации сообщений во время активного документа активен на месте в контейнере. Эти классы содержат приложения классы, производные от [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), и [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md). В контейнеры активных документов схемы OLE команд можно добавить только к [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-производного класса. Кроме того, в контейнеры активных документов **WM_COMMAND** сообщений будет отправлено только для схемы сообщений в `COleDocObjectItem`-производного класса.  
  
## <a name="ole-command-map-macros"></a>Макросы схемы команды OLE  
 Добавление функциональности карты команды в классе, используйте следующие макросы:  
  
```  
 
DECLARE_OLECMD_MAP ()  
 
```  
  
 Этот макрос переходит в объявлении класса (обычно в файле заголовка) класса, содержащего карты команд.  
  
```  
 
BEGIN_OLECMD_MAP(
theClass  ,   baseClass)  
 
```  
  
 `theClass`  
 Имя класса, содержащего карты команд.  
  
 `baseClass`  
 Имя класса базового класса, который содержит карты команд.  
  
 Этот макрос отмечает начало карты команд. Используйте этот макрос в файле реализации для класса, содержащего карты команд.  
  
```  
 
END_OLECMD_MAP()  
 
```  
  
 Этот макрос отмечает конец карты команд. Используйте этот макрос в файле реализации для класса, содержащего карты команд. Этот макрос всегда должны следовать **BEGIN_OLECMD_MAP** макрос.  
  
```  
 
ON_OLECMD(
pguid  ,   
olecmdid  ,
    id)  
 
```  
  
 `pguid`  
 Указатель на идентификатор GUID группы команд команды OLE. Этот параметр является **NULL** для стандартной группы команд OLE.  
  
 *olecmdid*  
 Идентификатор команды OLE вызывать команду.  
  
 `id`  
 Идентификатор **WM_COMMAND** сообщение должно отправляться приложения, содержащего карты команд при вызове этой команды OLE.  
  
 Используйте `ON_OLECMD` макрос в схеме команду для добавления записей для OLE команд для обработки. При получении команд OLE, они будут преобразованы в указанный **WM_COMMAND** сообщение и передавать через схему сообщений приложения, с помощью стандартной архитектуры маршрутизация команд MFC.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как добавить возможности обработки команд OLE MFC активный документ сервер для обработки [OLECMDID_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264) команды OLE. В примере предполагается, что использовался мастер приложений для создания приложения MFC, который служит сервером активного документа.  
  
1.  В вашей `CView`-производного класса заголовка файла, добавьте `DECLARE_OLECMD_MAP` макрос к объявлению класса.  
  
    > [!NOTE]
    >  Используйте `CView`-производного класса, так как он является одним из классов в сервера активных документов в **WM_COMMAND** цепочки маршрутизации сообщений.  
  
 ```  
    class CMyServerView : public CView  
 {  
    protected: // create from serialization only  
    CMyServerView();
DECLARE_DYNCREATE(CMyServerView)  
    DECLARE_OLECMD_MAP() 
 . . .  
 };  
 ```  
  
2.  В файле реализации для `CView`-производного класса, добавьте `BEGIN_OLECMD_MAP` и `END_OLECMD_MAP` макросы:  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
 
    END_OLECMD_MAP() 
 ```  
  
3.  Для обработки стандартную команду печати OLE, добавить [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) макрос команды карты, указав идентификатор команды OLE для стандартную команду печати и **ID_FILE_PRINT** для **WM_COMMAND**  Идентификатор. **ID_FILE_PRINT** — это стандарт, идентификатор команды print, используемых приложениями MFC, созданный мастером приложений:  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView,
    CView)  
    ON_OLECMD(NULL,
    OLECMDID_PRINT,
    ID_FILE_PRINT) 
    END_OLECMD_MAP() 
 ```  
  
 Обратите внимание, что один из стандартных макрос команды OLE, определенные в afxdocob.h, могут использоваться вместо `ON_OLECMD` макроса из-за **OLECMDID_PRINT** имеет стандартный идентификатор команды OLE. `ON_OLECMD_PRINT` Макрос будет выполнения той же задачи, как `ON_OLECMD` макрос, показанном выше.  
  
 Когда приложение контейнера отправляет этот сервер **OLECMDID_PRINT** команду через сервер `IOleCommandTarget` интерфейс MFC печати обработчик команды будет вызван на сервере, вызывающие сбои сервера печати приложения. Контейнер активного документа код для вызова команды print, добавленного в шагах выше будет выглядеть примерно следующим образом:  
  
```  
void CContainerCntrItem::DoOleCmd()  
{  
    IOleCommandTarget *pCmd = NULL;  
    HRESULT hr = E_FAIL;  
    OLECMD ocm={OLECMDID_PRINT, 0};  
 
    hr = m_lpObject->QueryInterface(IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if(FAILED(hr)) 
    return; 
 
    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if(SUCCEEDED(hr)&& (ocm.cmdf& OLECMDF_ENABLED))  
 { *//Command is available and enabled so call it  
    COleVariant vIn;  
    COleVariant vOut;  
    hr = pCmd->Exec(NULL, OLECMDID_PRINT,  
    OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);

    ASSERT(SUCCEEDED(hr));

 }  
    pCmd->Release();

} 
```  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)
