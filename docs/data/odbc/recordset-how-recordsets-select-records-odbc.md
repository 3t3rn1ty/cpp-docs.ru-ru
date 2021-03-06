---
title: 'Набор записей: Порядок выборки записей (ODBC) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c8bd84cf7f3dabb837cc7fff345d4ed6c41be44a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051364"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>Набор записей. Порядок выборки записей в наборе (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.  
  
Содержание раздела:  
  
- [Роль пользователя и вариантах при выборе записей](#_core_your_options_in_selecting_records).  
  
- [Как набор инструкций SQL и выбирает записи](#_core_how_a_recordset_constructs_its_sql_statement).  
  
- [Что можно сделать для настройки выделения](#_core_customizing_the_selection).  
  
Наборы записей для выбора записей из источника данных с помощью драйвера ODBC, отправляя инструкции SQL для драйвера. SQL зависят от того, как проектировать и откройте класса набора записей.  
  
##  <a name="_core_your_options_in_selecting_records"></a> Варианты при выборе записи  

Ниже приведены варианты при выборе записей.  
  
### <a name="how-and-when-you-can-affect-a-recordset"></a>Как и когда может повлиять на набор записей  
  
|Когда вы|Можно|  
|--------------|-------------|  
|Объявление класса набор записей с **Добавление класса** мастера|Укажите, какую таблицу необходимо выбрать из.<br /><br /> Укажите столбцы для включения.<br /><br /> См. в разделе [Добавление потребителя MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|  
|Завершения реализации класса набор записей|Переопределение функций-членов, таких как `OnSetOptions` (Дополнительно) чтобы задать параметры конкретного приложения или изменить значения по умолчанию. Укажите параметризованные члены данных, если вы хотите, чтобы параметризированные наборы записей.|  
|Создайте объект набора записей (перед вызовом метода `Open`)|Укажите условие поиска (возможно составных) для использования в **ГДЕ** предложение, которое фильтрует записи. См. в разделе [набор записей: фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Задать порядок сортировки для использования в **ORDER BY** записей предложения. См. в разделе [набор записей: сортировка записей (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Укажите значения параметров для любых параметров, добавленных к классу. См. в разделе [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|  

| Выполнение запроса набора записей посредством вызова метода `Open`| Укажите пользовательская строка для замены строки SQL по умолчанию, настроить с помощью мастера. См. в разделе [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) в *класса Справочник по библиотеке* и [SQL: Настройка инструкции SQL набора записей (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |  

| Вызовите `Requery` для запроса последними значениями из источника данных | Укажите новые параметры фильтрации и сортировки. См. в разделе [набор записей: выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> Как набор инструкций SQL  

При вызове объекта recordset [откройте](../../mfc/reference/crecordset-class.md#open) функции-члена `Open` создает инструкцию SQL, используя некоторые или все из следующих компонентов:  
  
- *LpszSQL* параметр, передаваемый `Open`. Если значение не NULL, этот параметр задает пользовательскую строку SQL или частью одного. Платформа выполняет синтаксический анализ строки. Если строка SQL **ВЫБЕРИТЕ** инструкции или ODBC **ВЫЗОВИТЕ** инструкции, framework используется в качестве инструкции SQL набора записей. Если строка не начинается с «SELECT» или «{CALL», платформа используется для создания SQL **FROM** предложение.  
  
- Строка, возвращаемая [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql). По умолчанию это имя таблицы, которую вы указали для набора записей в мастере, но можно изменить, функция возвращает. Платформа вызывает `GetDefaultSQL` , если строка не начинается с «SELECT» или «{CALL», он считается именем таблицы, который используется для создания строки SQL.  
  

- Элементами данных полей в наборе записей, которые связываются с конкретными столбцами таблицы. Столбцы записей автоматически связываются с адресами этих членов, используя их в качестве буфера. Платформа определяет корреляцию поля элементов данных со столбцами таблицы из [RFX](../../data/odbc/record-field-exchange-using-rfx.md) или вызовы функций Bulk RFX в наборе записей [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [DoBulkFieldExchange ](../../mfc/reference/crecordset-class.md#dofieldexchange) функция-член.  
  
- [Фильтра](../../data/odbc/recordset-filtering-records-odbc.md) для набора записей, если таковые имеются, содержащихся в [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) элемент данных. Инфраструктура использует эту строку для создания SQL **ГДЕ** предложение.  
  
- [Сортировки](../../data/odbc/recordset-sorting-records-odbc.md) order для набора записей, если он имеется, содержится в [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) элемент данных. Инфраструктура использует эту строку для создания SQL **ORDER BY** предложение.  

  
    > [!TIP]
    >  Для использования SQL **GROUP BY** предложение (и, возможно, **HAVING** предложение), добавьте предложения в конец строки фильтра.  
  
- Значения любого [параметризованные члены данных](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) вами для класса. Значения параметров задаются только в том случае, перед вызовом метода `Open` или `Requery`. Значения параметров, автоматически связываются «?» заполнителей в строке SQL. Во время компиляции укажите строку с заполнителями. Во время выполнения автоматически заполняются на основе значений параметров, которые можно передать сведения.  
  
`Open` Создает SQL **ВЫБЕРИТЕ** инструкции из этих компонентов. См. в разделе [Настройка выборки](#_core_customizing_the_selection) Дополнительные сведения об использовании компонентов .NET framework.  
  
После построения инструкции, `Open` SQL передает диспетчер драйверов ODBC (и библиотека курсоров ODBC, если он находится в памяти), который отправляет на драйвер ODBC для конкретной СУБД. Драйвер взаимодействует с СУБД для выборки в источнике данных и извлекает первую запись. Платформа загружает запись в элементами данных полей в наборе записей.  
  
Сочетание этих методов можно использовать, чтобы открыть [таблиц](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) и для создания запроса на основе [соединения](../../data/odbc/recordset-performing-a-join-odbc.md) нескольких таблиц. С помощью дополнительной настройки можно вызвать [предопределенные запросы](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (хранимые процедуры), выберите таблицу столбцы, которые не были известны во время разработки и [привязать](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) их к полям набора записей также можно выполнять большей части прочих задачи доступа к данным. Задачи, которые не удается выполнить наборов записей по-прежнему достигается за счет [вызов функций ODBC API](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) или выполнение инструкций SQL и [помощью функции CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).  
  
##  <a name="_core_customizing_the_selection"></a> Настройка выборки  

Помимо определения фильтра, порядок сортировки или параметры, можно выполнить следующие действия для настройки выбора набора записей:  
  
- Передача пользовательской строки SQL в *lpszSQL* при вызове [откройте](../../mfc/reference/crecordset-class.md#open) для набора записей. Что-либо передать *lpsqSQL* имеет приоритет над тем, какие [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) функция-член возвращает.  
  
     Дополнительные сведения см. в разделе [SQL: инструкция SQL Настройка набора записей (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md), который описывает типы инструкций SQL (или частичного инструкций) можно передать `Open` и что платформа делает с ними.  
  
    > [!NOTE]
    >  Если строка клиента, указываемые не начинается с «SELECT» или «{CALL», MFC предполагается, что он содержит имя таблицы. Это также относится к следующему элементу маркированного списка.  
  
- Изменение строки, которая мастер осуществляет запись в наборе записей `GetDefaultSQL` функция-член. Измените код функции, чтобы изменить его возвращает. По умолчанию мастер записывает `GetDefaultSQL` функция, возвращающая имя одиночной таблицы.  
  
     Может иметь `GetDefaultSQL` возвращает какие-либо элементов, которые можно передать в *lpszSQL* параметр `Open`. Если вы не передаете пользовательская строка SQL *lpszSQL*, используется строка, `GetDefaultSQL` возвращает. Как минимум `GetDefaultSQL` должно возвращать имя одной таблицы. Но чтобы можно было возвращать имена нескольких таблиц, полной **ВЫБЕРИТЕ** инструкции ODBC **ВЫЗОВИТЕ** инструкции и т. д. Что можно передать список *lpszSQL* — или иметь `GetDefaultSQL` возвращают — см. в разделе [SQL: инструкция SQL Настройка набора записей (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
     Если выполняется объединение двух или более таблиц, перепишите `GetDefaultSQL` настроить список таблиц, используемых в инструкции SQL, **FROM** предложение. Дополнительные сведения см. в разделе [набор записей: выполнение Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  

- Вручную привязать дополнительные поля элементов данных, возможно, основываясь на информация, представленная о схеме из источника данных во время выполнения. Добавление поля элементов данных для класса набора записей, [RFX](../../data/odbc/record-field-exchange-using-rfx.md) или вызывает функции Bulk RFX для них [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) функции-члена и Инициализация элементов данных в конструкторе класса. Дополнительные сведения см. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
- Переопределение функций-членов набора записей, таких как `OnSetOptions`, чтобы задать параметры конкретного приложения или переопределить значения по умолчанию.  
  
Если вы хотите создать набор записей на сложная инструкция SQL, необходимо использовать сочетание описанных выше способов настройки. Например возможно, вы хотите использовать предложения SQL и ключевые слова, не поддерживаемого непосредственно компонентом наборы записей или таким образом можно объединять несколько таблиц.  
  
## <a name="see-also"></a>См. также  

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей. Порядок обновления записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[Основы ODBC](../../data/odbc/odbc-basics.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Набор записей. Блокировка (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)