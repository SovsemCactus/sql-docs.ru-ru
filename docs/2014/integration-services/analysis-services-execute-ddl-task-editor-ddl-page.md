---
title: Редактор задачи «Выполнение инструкции DDL Analysis Services» (страница «DDL») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: janinezhang
ms.author: janinez
ms.openlocfilehash: 7cb1c84cccf4123f6ca1894baba5676937d80a15
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84925645"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a>Редактор задачи «Выполнение инструкции DDL служб Analysis Services» (страница DDL)
  Используйте страницу **DDL** диалогового окна **Редактор задачи "Выполнение инструкции DDL служб аналитики"** , чтобы настроить соединение с проектом [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или базой данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а также предоставить сведения об источнике инструкций языка определения данных (DDL).  
  
 Дополнительные сведения об этой задаче см. в разделе [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).  
  
## <a name="static-options"></a>Статические параметры  
 **Соединение**  
 Выберите [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] проект или [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Диспетчер соединений из списка или нажмите \<**New connection...**> и используйте диалоговое окно **Добавление Analysis Services диспетчера соединений** , чтобы создать новое соединение.  
  
 **См. также:** [Добавление диалогового окна "Диспетчер соединений со службами Analysis Services" в справочнике по пользовательскому интерфейсу](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Диспетчер соединений служб Analysis Services](connection-manager/analysis-services-connection-manager.md)  
  
 **Тип источника**  
 Указать тип источника инструкции DDL. Параметры этого свойства приведены в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Установите в качестве источника инструкцию DDL, содержащуюся в текстовом поле **SourceDirect** . При выборе этого значения в следующем подразделе отображаются динамические параметры.|  
|**Соединение с файлом**|В качестве источника указывается файл, содержащий инструкцию DDL. При выборе этого значения в следующем подразделе отображаются динамические параметры.|  
|**Переменная**|Установите в качестве источника переменную. При выборе этого значения в следующем подразделе отображаются динамические параметры.|  
  
## <a name="dynamic-options"></a>Динамические параметры  
  
### <a name="sourcetype--direct-input"></a>SourceType = Прямой ввод  
 **Source**  
 Введите инструкции DDL или нажмите кнопку с многоточием **(...)** и введите инструкции в диалоговом окне **инструкции DDL** .  
  
### <a name="sourcetype--file-connection"></a>SourceType = Подключение файла  
 **Source**  
 Выберите соединение с файлом в списке или нажмите \<**New connection...**> и используйте диалоговое окно **Диспетчер подключения файлов** , чтобы создать новое соединение.  
  
 **См. также:** [Диспетчер соединения файлов](connection-manager/file-connection-manager.md)  
  
### <a name="sourcetype--variable"></a>SourceType = Переменная  
 **Source**  
 Выберите переменную из списка или нажмите \<**New variable...**> и используйте диалоговое окно **Добавление переменной** , чтобы создать новую переменную.  
  
 **См. также:** [Переменные в службах Integration Services](integration-services-ssis-variables.md)  
  
## <a name="see-also"></a>См. также:  
 [Справочник по ошибкам и сообщениям Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Редактор задачи "Analysis Services выполнение инструкции DDL" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md)   
 [Страница "выражения"](expressions/expressions-page.md)   
 [Поток управления](control-flow/control-flow.md)   
 [Справочник по языку сценариев Analysis Services &#40;языка ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla)   
 [Справочник по XML для аналитики (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
