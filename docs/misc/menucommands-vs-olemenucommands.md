---
title: "команды MenuCommand и OleMenuCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "команды, создание в пакетах VSPackage"
  - "кнопки команд, создание и размещение"
  - "меню, создание команд"
ms.assetid: 553d5e07-3e19-4aba-b490-6c7dd05fd82e
caps.latest.revision: 46
caps.handback.revision: 46
manager: "douge"
---
# команды MenuCommand и OleMenuCommand
Вы можете создавать команды меню на основе объекта <xref:System.ComponentModel.Design.MenuCommand> или <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> и реализовывать соответствующие обработчики событий. В большинстве случаев можно использовать <xref:System.ComponentModel.Design.MenuCommand>, как это делает шаблон проекта VSPackage, но иногда может потребоваться использовать <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>.  
  
 Команды, которые VSPackage делает доступными в IDE, должны быть видимы и включены, чтобы пользователь смог их применять. Если команды создаются в VSCT\-файле с помощью шаблона Visual Studio Package для проектов, то они видимы и включены по умолчанию. Устанавливая некоторые флаги команд, например `DynamicItemStart`, можно изменить это поведение по умолчанию. Видимость, включенность и другие свойства команды также можно изменять в коде во время выполнения, обратившись к объекту <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>, связанному с командой.  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства необходимо установить пакет SDK для Visual Studio. Для получения дополнительной информации см. [SDK для Visual Studio](../Topic/Visual%20Studio%20SDK.md).  
  
## Расположения для шаблона пакета Visual Studio  
 Шаблон Visual Studio Package можно найти в диалоговом окне **Создание проекта**, развернув узлы **Visual Basic\/Extensibility** \(Visual Basic\/Расширение среды\), **C\#\/Extensibility** \(C\#\/Расширение среды\) или **Другие типы проектов\/Расширение среды**.  
  
## Создание команды  
 Все команды, группы команд, меню, панели инструментов и окна инструментов определяются в VSCT\-файле. Дополнительные сведения см. в разделе [Таблицы команд Visual Studio \(. Файлы Vsct\)](../Topic/Visual%20Studio%20Command%20Table%20\(.Vsct\)%20Files.md).  
  
 Если вы создаете VSPackage с помощью шаблона пакета, выберите пункт **Команда меню**, чтобы создать VSCT\-файл и определить команду меню по умолчанию. Для получения дополнительной информации см. [Создание расширения с помощью команды меню](../Topic/Creating%20an%20Extension%20with%20a%20Menu%20Command.md).  
  
#### Добавление команды в IDE  
  
1.  Откройте VSCT\-файл.  
  
2.  В разделе `Symbols` найдите элемент [GuidSymbol](../Topic/GuidSymbol%20Element.md), содержащий группы и команды.  
  
3.  Создайте по элементу [IDSymbol](../Topic/IDSymbol%20Element.md) для каждого меню, группы и команды, которые нужно добавить, как показано в следующем примере.  
  
     [!CODE [ButtonGroup#01](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#01)]  
  
     Атрибуты `name` элементов `GuidSymbol` и `IDSymbol` предоставляют пару GUID:ID для каждого нового меню, группы или команды.`guid` представляет набор команд, определенных для вашего VSPackage. Можно определить несколько наборов команд. Каждая пара GUID:ID должна быть уникальной.  
  
4.  В разделе [Buttons](../Topic/Buttons%20Element.md) создайте элемент [Button](../Topic/Button%20Element.md) \(кнопка\) для определения команды, как показано в следующем примере.  
  
     [!CODE [ButtonGroup#03](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#03)]  
  
    1.  Задайте поля `guid` и `id`, чтобы они соответствовали GUID:ID новой команды.  
  
    2.  Задайте атрибут `priority`.  
  
         Атрибут `priority` используется VSCT\-файлом для определения расположения кнопки среди других объектов в родительской группе.  
  
         Команды, имеющие более низкий приоритет, отображаются над командами с более высоким приоритетом или слева от них. Одинаковые значения приоритета разрешены, но относительное расположение команд с одинаковым приоритетом определяется порядком, в котором пакеты VSPackage обрабатываются во время выполнения, и этот порядок нельзя определить заранее.  
  
         Если атрибут `priority` пропустить, он получает значение 0.  
  
    3.  Задайте атрибут `type`. В большинстве случаев его значение будет равно `"Button"`. Описание других допустимых типов кнопки см. в разделе [Элемент Button](../Topic/Button%20Element.md).  
  
5.  В определении кнопки создайте элемент [Strings](../Topic/Strings%20Element.md), включающий элемент [ButtonText](../Topic/ButtonText%20Element.md), который содержит имя меню, отображаемое в IDE, и элемент [CommandName](../Topic/CommandName%20Element.md), который содержит имя команды, используемой для доступа к этому меню в окне **Команда**.  
  
     Если строка текста кнопки содержит символ &, пользователь может открыть меню, нажав клавишу ALT и клавишу, указанную после символа &.  
  
     При добавлении элемента `Tooltip` содержащийся в нем текст будет отображаться, когда пользователь наведет указатель на кнопку.  
  
6.  Добавьте элемент [Icon](../Topic/Icon%20Element.md), чтобы указать значок, который должен отображаться с командой. Значки требуются для кнопок на панели инструментов, но не для пунктов меню. Поля `guid` и `id` элемента `Icon` должны соответствовать таким же полям элемента [Bitmap](../Topic/Bitmap%20Element.md), определенного в разделе `Bitmaps`.  
  
7.  Добавьте флаги команды, чтобы соответствующим образом изменить внешний вид и поведение кнопки. Для этого добавьте элемент [CommandFlag](../Topic/Command%20Flag%20Element.md) в определение меню.  
  
8.  Задайте родительскую группу команды. Родительская группа может быть создаваемой группой, группой из другого пакета или группой из IDE. Например, чтобы добавить команду в панель инструментов редактирования Visual Studio рядом с кнопками **Комментарий** и **Удалить комментарий**, задайте родительскую группу guidStdEditor:IDG\_VS\_EDITTOOLBAR\_COMMENT. Если родительская группа является определяемой пользователем, она должна быть дочерним элементом меню, панели инструментов или окна инструментов в IDE.  
  
     В зависимости от проекта это можно сделать одним из двух способов.  
  
    -   В элементе `Button` создайте элемент [Parent](../Topic/Parent%20Element.md) и укажите в его полях `guid` и `id` Guid и ID \(идентификатор\) группы, где будет размещаться команда, которая также называется *основной родительской группой*.  
  
         В следующем примере задается команда, которая будет отображаться в определяемом пользователем меню.  
  
         [!CODE [TopLevelMenu#03](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#03)]  
  
    -   Вы можете опустить элемент `Parent`, если команду предполагается размещать с помощью функции размещения команд. Создайте элемент [CommandPlacements](../Topic/CommandPlacements%20Element.md) перед разделом `Symbols` и добавьте элемент [CommandPlacement](../Topic/CommandPlacement%20Element.md), имеющий `guid` и `id` команды, `priority` и родительский объект, как показано в следующем примере.  
  
         [!CODE [ButtonGroup#04](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#04)]  
  
         Если создать несколько размещений команд, имеющих одинаковые пары GUID:ID и разные родительские группы, меню будет отображаться в нескольких местах. Дополнительные сведения см. в описании элемента [CommandPlacements](../Topic/CommandPlacements%20Element.md).  
  
     Дополнительные сведения о родительских связях и группах команд см. в разделе [Создание многократно используемых групп кнопок](../Topic/Creating%20Reusable%20Groups%20of%20Buttons.md).  
  
 На этом этапе команда будет отображаться в IDE, но не будет иметь никаких функций. Если команда была создана с помощью шаблона пакета, по умолчанию она будет иметь обработчик щелчка, выводящий сообщение.  
  
## Обработка новой команды  
 Большинство команд в управляемом коде может обрабатываться в Managed Package Framework \(MPF\) с помощью сопоставления команды с объектом <xref:System.ComponentModel.Design.MenuCommand> или <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> и реализации соответствующих обработчиков событий.  
  
 Для кода, использующего интерфейс <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> непосредственно для обработки команд, вы должны реализовать интерфейс <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> и его методы. Два наиболее важных метода — <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> и <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>.  
  
1.  Получите экземпляр <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService>, как показано в следующем примере.  
  
     [!code-cs[ButtonGroup#21](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_5.cs)]  
  
2.  Создайте объект <xref:System.ComponentModel.Design.CommandID>, имеющий в качестве параметров GUID и ID \(идентификатор\) команды для обработки, как показано в следующем примере.  
  
     [!code-cs[ButtonGroup#22](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_6.cs)]  
  
     Шаблон пакета Visual Studio предоставляет две коллекции, `GuidList` и `PkgCmdIDList`, для хранения идентификаторов GUID и идентификаторов ID команд. Для команд, которые были добавлены с помощью шаблона, они заполняются автоматически, но для команд, добавленных вручную, необходимо также добавить запись ID в класс `PkgCmdIdList`.  
  
     Кроме того, вы можете заполнить объект <xref:System.ComponentModel.Design.CommandID>, используя исходное строковое значение GUID и целочисленное значение ID.  
  
3.  Создайте экземпляр объекта <xref:System.ComponentModel.Design.MenuCommand> или <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>, определяющий метод, который обрабатывает команду вместе с <xref:System.ComponentModel.Design.CommandID>, как показано в следующем примере.  
  
     [!code-cs[ButtonGroup#23](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_7.cs)]  
  
     Для статических команд подходит <xref:System.ComponentModel.Design.MenuCommand>. Для динамического отображения пунктов меню требуются обработчики событий QueryStatus.<xref:Microsoft.VisualStudio.Shell.OleMenuCommand> добавляет событие <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>, которое происходит, когда открывается основное меню команды, и некоторые другие свойства, например <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Команды, созданные шаблоном проекта, по умолчанию передаются в объект <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> метода `Initialize()` класса пакета.  
  
4.  Для статических команд подходит <xref:System.ComponentModel.Design.MenuCommand>. Для динамического отображения пунктов меню требуются обработчики событий QueryStatus.<xref:Microsoft.VisualStudio.Shell.OleMenuCommand> добавляет событие <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>, которое происходит, когда открывается основное меню команды, и некоторые другие свойства, например <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Команды, созданные шаблоном проекта, по умолчанию передаются в объект <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> метода `Initialize()` класса пакета. Мастер Visual Studio реализует метод `Initialize` с помощью `MenuCommand`. Для динамического отображения пункта меню вы должны изменить это на `OleMenuCommand`, как показано на следующем шаге. Кроме того, чтобы изменить текст пункта меню, необходимо добавить флаг команды TextChanges на кнопку команды меню в VSCT\-файле, как показано в приведенном ниже примере.  
  
     [!CODE [MenuText#02](../CodeSnippet/VS_Snippets_VSSDK/menutext#02)]  
  
5.  Передайте новую команду меню в метод <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> интерфейса <xref:System.ComponentModel.Design.IMenuCommandService>. Для команд, создаваемых шаблоном проекта, это выполняется по умолчанию, как показано в следующем примере.  
  
     [!code-cs[ButtonGroup#24](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_9.cs)]  
  
6.  Реализуйте метод, который обрабатывает команду.  
  
#### Реализация QueryStatus  
  
1.  Событие QueryStatus происходит перед отображением команды. Это позволяет установить свойства данной команды в обработчике события до того, как пользователь получит доступ к команде. Этот метод доступен только командам, которые добавлены в качестве объектов <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>.  
  
     Добавьте объект `EventHandler` в событие <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> в объекте <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>, создаваемом для обработки команды, как показано в следующем примере \(`menuItem` — это экземпляр <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>\).  
  
     [!code-cs[MenuText#14](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_10.cs)]
     [!code-vb[MenuText#14](../misc/codesnippet/VisualBasic/menucommands-vs-olemenucommands_10.vb)]  
  
     Объект `EventHandler` получает имя метода, который вызывается при запросе состояния команды меню.  
  
2.  Реализуйте метод обработчика состояния запроса для команды. Параметр `object` `sender` можно привести к объекту <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>, который используется для задания различных атрибутов команды меню, включая ее текст. В следующей таблице показаны свойства в классе <xref:System.ComponentModel.Design.MenuCommand> \(от которого является производным класс <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> MPF\), соответствующие флагам <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>.  
  
    |Свойство MenuCommand|Флаг OLECMDF|  
    |--------------------------|------------------|  
    |<xref:System.ComponentModel.Design.MenuCommand.Checked%2A> \= `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
    |<xref:System.ComponentModel.Design.MenuCommand.Visible%2A> \= `false`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
    |<xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> \= `true`|<xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF>|  
  
     Чтобы изменить текст команды меню, используйте свойство <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A> в объекте <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>, как показано в следующем примере.  
  
     [!code-cs[MenuText#11](../misc/codesnippet/CSharp/menucommands-vs-olemenucommands_11.cs)]
     [!code-vb[MenuText#11](../misc/codesnippet/VisualBasic/menucommands-vs-olemenucommands_11.vb)]  
  
 MPF автоматически выполняет обработку в случае неподдерживаемых или неизвестных групп. Пока команда не будет добавлена в <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> с помощью метода <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A>, эта команда не поддерживается.  
  
### Обработка команд с помощью интерфейса IOleCommandTarget  
 Для кода, использующего интерфейс <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> напрямую, VSPackage должен реализовать методы <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> и <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> интерфейса <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>. Если VSPackage реализует иерархию проекта, вместо этих методов должны быть реализованы методы <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> и <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> интерфейса <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>.  
  
 Оба метода, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> и <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>, разработаны для получения в качестве входных данных одного `GUID` набора команд и массива идентификаторов команд. Рекомендуется, чтобы пакеты VSPackage полностью поддерживали эту концепцию нескольких идентификаторов в одном вызове. Однако поскольку VSPackage не вызывается из других пакетов VSPackage, вы можете предположить, что массив команд содержит только один идентификатор команды, так как методы <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> и <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> выполняются в строго определенном порядке. Дополнительные сведения о маршрутизации см. в разделе [Маршрутизация команд в пакеты VSPackage](../Topic/Command%20Routing%20in%20VSPackages.md).  
  
 Для кода, использующего интерфейс <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> непосредственно для обработки команд, вы должны реализовать метод <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> в VSPackage следующим образом для обработки команд.  
  
##### Реализация метода QueryStatus  
  
1.  Получите <xref:Microsoft.VisualStudio.VSConstants.S_OK> для допустимых команд.  
  
2.  Задайте элемент `cmdf` параметра `prgCmds`.  
  
     Значение элемента `cmdf` — это логическое объединение значений из перечисления <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> с помощью логического оператора ИЛИ \(`|`\).  
  
     Используйте соответствующее перечисление, в зависимости от состояния команды.  
  
    -   Если команда поддерживается:  
  
         `prgCmds[0].cmdf = OLECMDF_SUPPORTED;`  
  
    -   Если команда должна быть невидимой в данный момент:  
  
         `prgCmds[0].cmdf |= OLECMDF_INVISIBLE;`  
  
    -   Если команда включена и отображается для выбора:  
  
         `prgCmds[0].cmdf |= OLECMDF_LATCHED;`  
  
         В случае обработки команд, которые размещаются в меню типа `MenuControllerLatched`, первая команда, помеченная флагом `OLECMDF_LATCHED`, — команда по умолчанию. Она отображается в меню при запуске. Дополнительные сведения о типах меню `MenuController` см. в разделе [Элемент меню](../Topic/Menu%20Element.md).  
  
    -   Если команда включена в текущий момент:  
  
         `prgCmds[0].cmdf |= OLECMDF_ENABLED;`  
  
    -   Если команда является частью контекстного меню и скрыта по умолчанию:  
  
         `prgCmds[0] cmdf |= OLECMDF_DEFHIDEONCTXMENU`  
  
    -   Если команда использует флаг `TEXTCHANGES`, задайте в элементе `rgwz` параметра `pCmdText` новый текст команды, а в элементе `cwActual` параметра `pCmdText` — размер командной строки.  
  
     В состояниях ошибок метод <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> должен обрабатывать следующие ошибки.  
  
    -   Если идентификатор GUID неизвестен или не поддерживается, должно возвращаться значение `OLECMDERR_E_UNKNOWNGROUP`.  
  
    -   Если идентификатор GUID известен, но идентификатор ID команды неизвестен или не поддерживается, должно возвращаться значение `OLECMDERR_E_NOTSUPPORTED`.  
  
 Реализация VSPackage метода <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> также должна возвращать конкретные коды ошибок, в зависимости от того, поддерживается ли команда и была ли она обработана успешно.  
  
##### Реализация метода Exec  
  
-   Если `GUID` команды неизвестен, должно возвращаться значение `OLECMDERR_E_UNKNOWNGROUP`.  
  
-   Если `GUID` известен, но ID команды неизвестен, должно возвращаться значение `OLECMDERR_E_NOTSUPPORTED`.  
  
-   Если `GUID` и ID команды соответствуют паре GUID:ID, которая используется командой в VSCT\-файле, выполните код, связанный с командой, и верните значение <xref:Microsoft.VisualStudio.VSConstants.S_OK>.  
  
## См. также  
 [Справочник по схемам VSCT XML](../Topic/VSCT%20XML%20Schema%20Reference.md)   
 [Расширение меню и команд](../Topic/Extending%20Menus%20and%20Commands.md)