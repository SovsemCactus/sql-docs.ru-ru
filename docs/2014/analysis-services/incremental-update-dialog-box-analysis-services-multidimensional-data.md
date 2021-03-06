---
title: Диалоговое окно «Добавочное обновление» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.incrementalupdate.f1
ms.assetid: d5a5ae27-44e7-4179-b9e2-efbf21d6c5f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6115a5123fd6e72cee0ebccaac5f539be8aebfbe
ms.sourcegitcommit: f0772f614482e0b3cde3609e178689ce62ca3a19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84544176"
---
# <a name="incremental-update-dialog-box-analysis-services---multidimensional-data"></a>Диалоговое окно «Добавочное обновление» (службы Analysis Services — многомерные данные)
  С помощью диалогового окна **Добавочное обновление** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] можно определить параметры, которые используются при добавочных обновлениях групп мер и секций. Диалоговое окно **Добавочное обновление** отображается при щелчке **Настроить** в столбце **Установки** сетки **Список объектов** в диалоговом окне **Обработка** .  
  
## <a name="options"></a>Варианты  
  
|Термин|Определение|  
|----------|----------------|  
|**Группа мер**|Выберите группу мер для добавочного обновления.<br /><br /> Примечание. Этот параметр включен только при выполнении добавочного обновления куба. При добавочном обновлении группы мер или секции этот параметр отключен.|  
|**Partition (Раздел)**|Выберите секцию для обновления.<br /><br /> Примечание. Этот параметр включен только при выполнении добавочного обновления куба. При добавочном обновлении группы мер или секции этот параметр отключен.|  
|**Таблица**|Щелкните для обновления объекта из таблицы.|  
|**Источник данных или представление**|Выберите источник данных или представление источника данных, в котором находится исходная таблица.<br /><br /> Примечание. Этот параметр включен, если выбран источник данных **Таблица** .|  
|**Схема и имя таблицы**|Выберите исходную таблицу, используемую для получения данных для добавочного обновления куба, группы мер или секции.<br /><br /> Примечание. Этот параметр включен, если выбран источник данных **Таблица** .|  
|**Запрос**|Щелкните для обновления объекта из запроса.|  
|**Источник данных**|Выберите источник данных, в котором находятся таблицы, к которым должен выполняться запрос.<br /><br /> Примечание. Этот параметр включен, если выбран источник данных **Очередь** .|  
|**Текст запроса**|Введите текст запроса, используемого для получения данных для добавочного обновления куба, группы мер или секции.<br /><br /> Примечание. Этот параметр включен, если выбран источник данных **Очередь** .|  
  
## <a name="see-also"></a>См. также:  
 [Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)   
 [Диалоговое окно "обработка" &#40;Analysis Services многомерных данных&#41;](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
