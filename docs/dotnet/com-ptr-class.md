---
title: "Класс com::ptr | Microsoft Docs"
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
  - "com::ptr"
  - "msclr::com::ptr"
  - "msclr.com.ptr"
  - "com.ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr - класс"
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс com::ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Программа\-оболочка для com\-объекта, который можно использовать в качестве члена класса среды CLR.  Программа\-оболочка также автоматизирует управления временем существования com\-объекта, освобождая все ссылки, принадлежащие объекта при его вызове деструктора.  Аналогичный в [CComPtr Class](../atl/reference/ccomptr-class.md).  
  
## Синтаксис  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### Параметры  
 `_interface_type`  
 Интерфейс модели COM.  
  
## Заметки  
 `com::ptr` также можно использовать в качестве локальной переменной функции для упрощения задачи различные модели COM и автоматизации управления временем существования.  
  
 `com::ptr` не может использоваться непосредственно в качестве параметра функции; используйте [Оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md) или [Оператор дескриптора объекта \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
 `com::ptr` непосредственно возврата из функции; используйте вместо этого дескриптора.  
  
## Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` для создания его объект `IXMLDOMDocument` закрытого члена.  Вызова открытых методов класса возникает при вызовах, который содержит объект `IXMLDOMDocument`.  Пример создает экземпляр XML\-документа, заполняет его с простого XML, а также упрощенную проверку узлов в схеме разобранную документации для печати XML на консоль.  
  
```  
// comptr.cpp  
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
  
   void LoadXml(String^ xml) {  
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);  
      BSTR bstr = NULL;  
  
      try {  
         // load some XML into the document  
         bstr = ::SysAllocString(pinnedXml);  
         if (NULL == bstr) {  
            throw gcnew OutOfMemoryException;  
         }  
         VARIANT_BOOL bIsSuccessful = false;  
         // use operator -> to call IXMODOMDocument member function  
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   // simplified function to write just the first xml node to the console  
   void WriteXml() {  
      IXMLDOMNode* pNode = NULL;  
  
      try {  
         // the first child of the document is the first real xml node  
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));  
         if (NULL != pNode) {  
            WriteNode(pNode);  
         }  
      }  
      finally {  
         if (NULL != pNode) {  
            pNode->Release();  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   // simplified function that only writes the node  
   void WriteNode(IXMLDOMNode* pNode) {  
      BSTR bstr = NULL;  
  
      try {  
         // write out the name and text properties  
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));  
         String^ strName = gcnew String(bstr);  
         Console::Write("<{0}>", strName);  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));  
         Console::Write(gcnew String(bstr));  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Console::WriteLine("</{0}>", strName);  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // stream some xml into the document  
      doc.LoadXml("<word>persnickety</word>");  
  
      // write the document to the console  
      doc.WriteXml();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **\<word\>persnickety\<\/word\>**   
## Требования  
 **Файл заголовка**\<msclr\\com\\ptr.h\>  
  
 **Пространство имен** msclr::com  
  
## См. также  
 [Библиотека поддержки C\+\+](../dotnet/cpp-support-library.md)   
 [Члены ptr](../dotnet/ptr-members.md)