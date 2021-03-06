---
title: Редактор задачи «XML» (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmltask.general.f1
helpviewer_keywords:
- XML Task Editor
ms.assetid: b9622c48-3243-4408-a1de-9ba20e32ff70
author: janinezhang
ms.author: janinez
ms.openlocfilehash: 26055dde636d299a2a58fdfe0bdbd3fdfbdab012
ms.sourcegitcommit: f71e523da72019de81a8bd5a0394a62f7f76ea20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84972354"
---
# <a name="xml-task-editor-general-page"></a>Редактор задачи «XML» (страница «Общие»)
  Используйте **Узел «Общие»** диалогового окна **Редактор задачи «XML»** для задания типа и настройки операции.  
  
 Дополнительные сведения об этой задаче см. в разделе [XML Task](control-flow/xml-task.md). Дополнительные сведения о работе с XML-документами и данными см. в разделе «[Employing XML in the .NET Framework](https://go.microsoft.com/fwlink/?LinkId=56214)» в библиотеке MSDN.  
  
## <a name="static-options"></a>Статические параметры  
 **OperationType**  
 Выберите из списка тип операции. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Проверка**|Проверяется соответствие XML-документа определению типа документа (DTD) или схеме определения XML-схемы (XSD, XML Schema definition). При выборе этого параметра в разделе отображаются динамические параметры **Проверить**.|  
|**XSLT**|Выполняет преобразование XSL в XML-документах. При выборе этого параметра в разделе отображаются динамические параметры **XSLT**.|  
|**ФОРМАТЕ**|Выполняет запросы и вычисления XPath. При выборе этого параметра в разделе отображаются динамические параметры **XPATH**.|  
|**Объединить**|Выполняет слияние двух XML-документов. При выборе этого параметра отображаются динамические параметры в разделе **Слияние**.|  
|**Разницы**|Сравнивает два XML-документа. При выборе этого параметра отображаются динамические параметры в разделе **Поиск различий**.|  
|**Обновление**|Результат операции поиска различий применяется для создания нового документа. При выборе этого параметра в разделе отображаются динамические параметры **Обновление**.|  
  
 **Тип источника**  
 Выберите тип источника XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **Source**  
 Если параметр **Source** имеет значение **Прямой ввод**, укажите код XML или нажмите кнопку с многоточием **(...)**, а затем укажите код XML в диалоговом окне **Редактор исходного текста документа**.  
  
 Если параметр **источник** имеет значение **соединение с файлом**, выберите Диспетчер подключения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если параметр **Source** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, **\<New variable...>** чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
## <a name="operationtype-dynamic-options"></a>Динамические параметры OperationType  
  
### <a name="operationtype--validate"></a>OperationType = Проверка  
 Задайте параметры для операции проверки.  
  
 **SaveOperationResult**  
 Укажите, сохраняет ли задача «XML» вывод операции проверки.  
  
 **OverwriteDestination**  
 Укажите, перезаписывать ли файл или переменную назначения.  
  
 **Назначение**  
 Выберите существующий диспетчер соединения файлов или щелкните \<**New connection...**> , чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 **DestinationType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **ValidationType**  
 Выберите тип проверки. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**DTD**|Использование определения типа документа (DTD).|  
|**XSD**|Использование определения схемы XML (XSD). При выборе этого параметра в разделе отображаются динамические параметры **ValidationType**.|  
  
 **FailOnValidationFail**  
 Укажите, заканчивается ли операция с ошибкой, если не удается проверить документ.  
  
 **ValidationDetails**  
 Если значение свойства равно True, данные об ошибках будут содержать подробные сведения. Дополнительные сведения см. в разделе [Validate XML with the XML Task](control-flow/validate-xml-with-the-xml-task.md).  
  
### <a name="validationtype-dynamic-options"></a>Динамические параметры ValidationType  
  
#### <a name="validationtype--xsd"></a>ValidationType = XSD  
 **SecondOperandType**  
 Выберите тип источника второго XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperand**  
 Если параметр **SecondOperandType** имеет значение **Прямой ввод**, укажите XML-код или нажмите кнопку с многоточием **(...)**, а затем введите XML-код в диалоговом окне **Редактор источника**.  
  
 Если **параметр SecondOperandType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если **параметр XPathStringSourceType** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
### <a name="operationtype--xslt"></a>OperationType = XSLT  
 Задайте параметры для операции XSLT.  
  
 **SaveOperationResult**  
 Укажите, сохраняет ли задача «XML» вывод операции XSLT.  
  
 **OverwriteDestination**  
 Укажите, перезаписывать ли файл или переменную назначения.  
  
 **Назначение**  
 Если параметр **destinationType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если параметр **destinationType** имеет значение **variable**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperandType**  
 Выберите тип источника второго XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperand**  
 Если параметр **SecondOperandType** имеет значение **Прямой ввод**, укажите XML-код или нажмите кнопку с многоточием **(...)**, а затем введите XML-код в диалоговом окне **Редактор источника**.  
  
 Если **параметр SecondOperandType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если **параметр XPathStringSourceType** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
### <a name="operationtype--xpath"></a>OperationType = XPATH  
 Задайте параметры для операции XPath.  
  
 **SaveOperationResult**  
 Укажите, сохраняет ли задача «XML» вывод операции XPath.  
  
 **OverwriteDestination**  
 Укажите, перезаписывать ли файл или переменную назначения.  
  
 **Назначение**  
 Если параметр **destinationType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если параметр **destinationType** имеет значение **variable**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperandType**  
 Выберите тип источника второго XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperand**  
 Если параметр **SecondOperandType** имеет значение **Прямой ввод**, укажите XML-код или нажмите кнопку с многоточием **(...)**, а затем введите XML-код в диалоговом окне **Редактор источника**.  
  
 Если **параметр SecondOperandType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если **параметр XPathStringSourceType** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
 **PutResultInOneNode**  
 Укажите, записывается ли результат в один узел.  
  
 **XPathOperation**  
 Выберите тип результата операции XPath. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Аттестаци**|Возвращает результаты функции XPath.|  
|**Список узлов**|Возвращаются выбранные узлы в качестве фрагмента кода XML.|  
|**Значения**|Возвращает текстовые представления содержимого всех выбранных узлов, объединенные в одну строку.|  
  
### <a name="operationtype--merge"></a>OperationType = Объединение  
 Задайте параметры для операции объединения.  
  
 **XPathStringSourceType**  
 Выберите тип источника XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **XPathStringSource**  
 Если параметр **XPathStringSourceType** имеет значение **Прямой ввод**, укажите XML-код или нажмите кнопку с многоточием **(...)**, а затем введите XML-код в диалоговом окне **Редактор исходного текста документа**.  
  
 Если **параметр XPathStringSourceType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если **параметр XPathStringSourceType** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также**: [Integration Services &#40;переменные&#41; SSIS](integration-services-ssis-variables.md), [Добавить переменную](../../2014/integration-services/add-variable.md)  
  
 При использовании инструкции XPath для определения места в исходном документе, куда необходимо вставить данные, ожидается, что инструкция возвратит единственный узел. Если инструкция возвращает несколько узлов, то используется только первый узел. Содержимое второго документа добавляется в первый узел, который возвращается запросом XPath.  
  
 **SaveOperationResult**  
 Укажите, сохраняет ли задача «XML» вывод операции объединения.  
  
 **OverwriteDestination**  
 Укажите, перезаписывать ли файл или переменную назначения.  
  
 **Назначение**  
 Если параметр **destinationType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если параметр **destinationType** имеет значение **variable**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperandType**  
 Выберите тип получателя второго XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperand**  
 Если параметр **SecondOperandType** имеет значение **Прямой ввод**, укажите XML-код или нажмите кнопку с многоточием **(...)**, а затем укажите XML-код в диалоговом окне **Редактор исходного текста документа**.  
  
 Если **параметр SecondOperandType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если **параметр SecondOperandType** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также**: [Integration Services &#40;переменные&#41; SSIS](integration-services-ssis-variables.md), [Добавить переменную](../../2014/integration-services/add-variable.md)  
  
### <a name="operationtype--diff"></a>OperationType = инструмент сравнения  
 Задайте параметры для операции поиска различий.  
  
 **DiffAlgorithm**  
 Выберите алгоритм поиска различий, который будет использоваться при сравнении документов. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Автоматически**|Предоставьте задаче «XML» определить, использовать ли быстрый или точный алгоритм.|  
|**быстрый;**|Применение быстрого, но менее точного алгоритма поиска различий.|  
|**Точный**|Применение точного алгоритма поиска различий.|  
  
 **Параметры операции поиска различий**  
 Задание параметров, применяемых в операции поиска различия. Эти параметры перечисляются в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**IgnoreXMLDeclaration**|Укажите, сравнивать ли XML-декларации.|  
|**IgnoreDTD**|Укажите, пропускать ли обработку определения типа документа (DTD).|  
|**IgnoreWhite Spaces**|Укажите, пропускать ли различия в количестве пробелов при сравнении документов.|  
|**IgnoreNamespaces**|Укажите, сравнивать ли универсальный идентификатор ресурсов (URI) пространства имен элементов и имена атрибутов этих элементов.<br /><br /> Примечание. Если этот параметр имеет значение `True`, два элемента, имеющие одинаковое локальное имя, но разные пространства имен, считаются идентичными.|  
|**IgnoreProcessingInstructions**|Укажите, сравнивать ли инструкции по обработке.|  
|**IgnoreOrderOf ChildElements**|Укажите, сравнивать ли порядок дочерних элементов.<br /><br /> Примечание. Если этот параметр имеет значение `True`, дочерние элементы, отличающиеся только положением в списке одноуровневых элементов, считаются идентичными.|  
|**IgnoreComments**|Укажите, сравнивать ли узлы комментариев.|  
|**IgnorePrefixes**|Укажите, сравнивать ли префиксы элементов и имена атрибутов.<br /><br /> Примечание. Если этот параметр имеет значение `True`, два элемента, имеющие одинаковое локальное имя, но разные префиксы и коды URI пространств имен, считаются идентичными.|  
  
 **FailOnDifference**  
 Укажите, заканчивается ли задача с ошибкой, если не удается выполнить операцию поиска различий.  
  
 **SaveDiffGram**  
 Укажите, сохранять ли результаты сравнения в виде документа DiffGram.  
  
 **SaveOperationResult**  
 Укажите, сохраняет ли задача «XML» вывод операции поиска различий.  
  
 **OverwriteDestination**  
 Укажите, перезаписывать ли файл или переменную назначения.  
  
 **Назначение**  
 Если параметр **destinationType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если параметр **destinationType** имеет значение **variable**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperandType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperand**  
 Если параметр **SecondOperandType** имеет значение **Прямой ввод**, укажите XML-код или нажмите кнопку с многоточием **(...)**, а затем укажите XML-код в диалоговом окне **Редактор исходного текста документа**.  
  
 Если **параметр SecondOperandType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если **параметр SecondOperandType** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также**: [Integration Services &#40;переменные&#41; SSIS](integration-services-ssis-variables.md), [Добавить переменную](../../2014/integration-services/add-variable.md)  
  
### <a name="operationtype--patch"></a>OperationType = Patch  
 Задайте параметры для операции обновления.  
  
 **SaveOperationResult**  
 Укажите, сохраняет ли задача «XML» вывод операции обновления.  
  
 **OverwriteDestination**  
 Укажите, перезаписывать ли файл или переменную назначения.  
  
 **Назначение**  
 Если параметр **destinationType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если параметр **destinationType** имеет значение **variable**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также:**[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), [Добавление переменной](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperandType**  
 Выберите тип назначения XML-документа. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задайте источник для XML-документа.|  
|**Соединение с файлом**|Выберите файл, содержащий XML-документ.|  
|**Переменная**|В качестве источника задайте переменную, содержащую XML-документ.|  
  
 **SecondOperand**  
 Если параметр **SecondOperandType** имеет значение **Прямой ввод**, укажите XML-код или нажмите кнопку с многоточием **(...)**, а затем укажите XML-код в диалоговом окне **Редактор исходного текста документа**.  
  
 Если **параметр SecondOperandType** имеет значение **соединение с файлом**, выберите Диспетчер соединения файлов или щелкните, \<**New connection...**> чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Если **параметр SecondOperandType** имеет значение **переменная**, выберите существующую переменную или нажмите кнопку, \<**New variable...**> чтобы создать новую переменную.  
  
 **См. также**: [Integration Services &#40;переменные&#41; SSIS](integration-services-ssis-variables.md), [Добавить переменную](../../2014/integration-services/add-variable.md)  
  
## <a name="see-also"></a>См. также:  
 [Справочник по ошибкам и сообщениям Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Страница «Выражения»](expressions/expressions-page.md)  
  
  
