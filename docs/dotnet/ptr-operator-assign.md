---
title: "ptr::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr.operator="
  - "msclr.com.ptr.operator="
  - "msclr::com::ptr::operator="
  - "ptr::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator="
ms.assetid: 58619910-46c0-4db8-b183-c811b23b2df1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вложение com\-объекта в `com::ptr`.  
  
## Синтаксис  
  
```  
ptr<_interface_type> % operator=(  
   _interface_type * _right  
);  
```  
  
#### Параметры  
 `_right`  
 Указатель COM\-интерфейса, чтобы вложить.  
  
## Возвращаемое значение  
 Ссылка на отслеживания `com::ptr`.  
  
## Исключения  
 Если `com::ptr` уже имеет ссылку на com\-объекты, `operator=` создает <xref:System.InvalidOperationException>.  
  
## Заметки  
 Присвоящ com\-объекта в `com::ptr` ссылается на com\-объекты, но не освобождает ссылку вызывающего объекта в ней.  
  
 Этот оператор имеет тот же эффект, что и `Attach`.  
  
## Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` для создания его объект `IXMLDOMDocument` закрытого члена.  Сначала вызывает `Release` функции\-члена `ReplaceDocument` на любом ранее была объект и затем использовать `operator=` вложить новый объект документа.  
  
```  
// comptr_op_assign.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   // replace currently held COM object with another one  
   void ReplaceDocument(IXMLDOMDocument* pDoc) {  
      // release current document object  
      m_ptrDoc.Release();  
      // attach the new document object  
      m_ptrDoc = pDoc;  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// unmanaged function that creates a raw XML DOM Document object  
IXMLDOMDocument* CreateDocument() {  
   IXMLDOMDocument* pDoc = NULL;  
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,  
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));  
   return pDoc;  
}  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // get another document object from unmanaged function and  
      // store it in place of the one held by the ref class  
      pDoc = CreateDocument();  
      doc.ReplaceDocument(pDoc);  
      // no further need for raw object reference  
      pDoc->Release();  
      pDoc = NULL;  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
   finally {  
      if (NULL != pDoc) {  
         pDoc->Release();  
      }  
   }  
}  
```  
  
## Требования  
 **Файл заголовка**\<msclr\\com\\ptr.h\>  
  
 **Пространство имен** msclr::com  
  
## См. также  
 [Члены ptr](../dotnet/ptr-members.md)   
 [ptr::Attach](../dotnet/ptr-attach.md)   
 [ptr::Detach](../Topic/ptr::Detach.md)   
 [ptr::Release](../dotnet/ptr-release.md)