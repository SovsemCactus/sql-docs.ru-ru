---
title: Параметры схемы базы данных предметной области (мастер формирования схем) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7edc1fc89e9463c7482b47866aa3d12e1bc231a7
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84940245"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a>Параметры схемы базы данных предметной области (мастер формирования схем) (службы Analysis Services — многомерные данные)
  Используйте страницу **Параметры схемы базы данных предметной области** для управления формированием схемы, а также для определения типа сохранения данных.  
  
## <a name="options"></a>Варианты  
 **Схема-владелец**  
 Задает имя схемы в новой предметной области базы данных.  
  
 **Создать первичные ключи в таблицах измерений**  
 Позволяет создать первичные ключи в таблицах измерений в сформированной схеме. Если не установлен флажок создания индекса, то индекс не создается.  
  
> [!NOTE]  
>  Если этот флажок не установлен, применяется ссылочная целостность.  
  
 **Создать индексы**  
 Позволяет создать индексы во внешних ключевых столбцах в сформированной схеме.  
  
 **Обязательная целостность ссылок**  
 Позволяет задать целостность ссылок в сформированной схеме. Если этот флажок не установлен, связи создаются, но не задаются.  
  
 **Сохранить данные при повторном формировании**  
 Позволяет сохранить данные в предметной области базы данных после завершения работы мастера. Если этот флажок не установлен, все данные в предметной области базы данных могут быть удалены без выдачи предупреждения.  
  
 **Заполнить таблицы времени**  
 Позволяет указать, как мастер заполняет расписания. В следующей таблице показаны возможные значения для данного параметра.  
  
> [!NOTE]  
>  Этот параметр доступен, если мастер формирования схем вызван из проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] с помощью среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] в режиме проекта.  
  
|Применение|Описание|  
|-----------|-----------------|  
|Заполнить|Заполнение предметной области расписаний.|  
|Не заполнять|Предметная область расписаний не заполняется.|  
|Заполнить, если пуста|Предметная область расписаний заполняется, если она пуста.|  
  
## <a name="see-also"></a>См. также:  
 [Справка F1 мастера формирования схем &#40;Analysis Services многомерных данных&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  
