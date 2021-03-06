---
title: Свойства таблицы (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c140715b3f6c6003992ef42f6af6352de17c2c4
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84938635"
---
# <a name="table-properties-ssas-tabular"></a>Свойства таблицы (табличные службы SSAS)
  В этом разделе описаны свойства табличной модели. Описанные здесь свойства отличаются от свойств таблицы в диалоговом окне «Изменение свойств таблицы», которые определяют, какие столбцы из источника нужно импортировать.  
  
 Разделы данной темы:  
  
-   [Свойства таблицы](#bkmk_properties)  
  
-   [Настройка параметров табличных свойств](#bkmk_config_prop)  
  
##  <a name="table-properties"></a><a name="bkmk_properties"></a>Свойства таблицы  
 **Основной**  
  
|Свойство|Параметр по умолчанию|Описание|  
|--------------|---------------------|-----------------|  
|**Имя подключения**|\<connection name>|Имя соединения с источником данных таблицы.<br /><br /> Чтобы изменить соединение, нажмите кнопку.|  
|**Служеб**|False|Указывает, является ли таблица скрытой при выводе отчета о списке полей клиента.|  
|**Секции**||Секции для таблицы не могут отображаться в окне **Свойства** . Чтобы просмотреть, создать или изменить секции, нажмите эту кнопку и откройте диспетчер секций.|  
|**Исходные данные**||Исходные данные для таблицы не могут отображаться в окне **Свойства** . Чтобы просмотреть или изменить исходные данные, нажмите эту кнопку и откройте диалоговое окно «Изменение свойств таблицы».|  
|**Описание таблицы**||Текстовое описание для таблицы.<br /><br /> Если в программе [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)]навести указатель мыши на таблицу в списке полей, отобразится ее описание в виде подсказки.|  
|**Имя таблицы**|\<friendly name>|Указывает понятное имя таблицы. Имя таблицы можно указать при импорте с помощью мастера импорта таблиц или в любое время после импорта. Имя таблицы в модели может отличаться от имени связанной исходной таблицы. Понятное имя таблицы появляется в списке полей клиентского приложения, а также в базе данных model в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].|  
  
 **Свойства отчетов**  
  
 Подробное описание и сведения о настройке свойств создания отчетов см. в разделе [Свойства отчетов Power View (табличные службы SSAS)](properties-ssas-tabular.md).  
  
|Свойство|Параметр по умолчанию|Описание|  
|--------------|---------------------|-----------------|  
|**Набор полей по умолчанию**|||  
|Поведение таблиц|||  
  
###  <a name="to-configure-table-property-settings"></a><a name="bkmk_config_prop"></a>Настройка параметров свойств таблицы  
  
1.  В конструкторе моделей в представлении диаграмм щелкните таблицу (вкладку) или в представлении диаграмм щелкните заголовок таблицы.  
  
2.  В окне **Свойства** щелкните свойство и введите значение или нажмите кнопку для открытия дополнительных параметров конфигурации.  
  
  
