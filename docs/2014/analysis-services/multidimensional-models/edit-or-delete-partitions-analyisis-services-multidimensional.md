---
title: Изменение или удаление секций (Analysis Services — многомерные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying partitions
- partitions [Analysis Services], modifying
ms.assetid: fb7a64ca-d021-4926-b92d-83476fbc40a3
author: minewiskan
ms.author: owend
ms.openlocfilehash: cad4c1f70743cafcc428835b3dcd11e2fa26ee79
ms.sourcegitcommit: f0772f614482e0b3cde3609e178689ce62ca3a19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84546777"
---
# <a name="edit-or-delete-partitions-analyisis-services---multidimensional"></a>Изменение и удаление секций (Analysis Services — многомерные данные)
  Секции куба редактируются с помощью вкладки **Секции** в конструкторе кубов в [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)]. На вкладке **Секции** перечислены секции для всех групп мер в кубе. А также секции обратной записи с включенной функцией обратной записи.

 Чтобы изменить секции для любой группы мер, разверните группу мер на вкладке **Секции** . секции для группы мер перечислены по порядковому номеру в табличном формате со столбцами, перечисленными в следующей таблице.

 Настройки связанной группы мер необходимо редактировать в исходном кубе.

 Удаление секций производится автоматически при слиянии исходной секции с целевой. Секция, указанная как источник, после успешного слияния удаляется. Также можно вручную удалить секции в [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или на вкладке «Секции» в [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)]. Щелкните правой кнопкой мыши и выберите команду **Удалить**. Помните, что при удалении секции также удаляются данные и агрегирования. В качестве меры предосторожности обязательно создайте резервную копию базы данных на тот случай, что понадобится отменить данное действие.

> [!NOTE]
>  Также можно использовать XMLA-скрипты, автоматизирующие задачи по построению, слиянию и удалению секций. XMLA-скрипт может быть создан и выполнен в [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]или в пользовательских SSIS-пакетах, выполняемых как задача по расписанию. Дополнительные сведения см. в статье [Automate Analysis Services Administrative Tasks with SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).

## <a name="partition-source"></a>Источник секции
 Указывает исходную таблицу или именованный запрос для секции. Чтобы изменить исходную таблицу, щелкните ячейку, а затем нажмите кнопку обзора (**...**).

 ![Исходный столбец на панели секции](../media/ssas-partitionsource.png "Исходный столбец на панели секции")

 Если секция основывается на запросе, нажмите кнопку обзора (**...**), чтобы изменить запрос. Это изменит свойство **Source** секции. Дополнительные сведения см. [в разделе Изменение источника секции для использования другой таблицы фактов](change-a-partition-source-to-use-a-different-fact-table.md).

 Можно указать таблицу в представлении источника данных, которая имеет такую же структуру, как исходная таблица источника (во внешнем источнике данных, из которого извлекаются данные). Источник может быть в любом из источников данных или представлений источников данных базы данных куба.

## <a name="storage-settings"></a>Параметры хранилища
 В конструкторе кубов на вкладке секций можно щелкнуть **Параметры хранилища** , чтобы выбрать одну из стандартных настроек для реляционного хранилища ROLAP, гибридного HOLAP или многомерного MOLAP или установить пользовательские настройки для режима хранилища и упреждающего кэширования. По умолчанию используется хранилище MOLAP, поскольку оно обеспечивает наилучшую производительность запросов. Дополнительные сведения о каждом параметре см. в разделе [Определение хранилища секции (Analysis Services — многомерные данные)](set-partition-storage-analysis-services-multidimensional.md).

 Хранилище можно настроить отдельно для каждой секции каждой группы мер в кубе. Также можно установить настройки хранилища по умолчанию для куба или группы мер. Хранилище настраивается на вкладке **Секции** мастера кубов.

## <a name="see-also"></a>См. также:
 [Создание и управление локальной секцией &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md) [конструирования агрегатов &#40;Analysis Services-многомерные&#41;](designing-aggregations-analysis-services-multidimensional.md) [слияние секций в Analysis Services &#40;SSAS — многомерные&#41;](merge-partitions-in-analysis-services-ssas-multidimensional.md)


