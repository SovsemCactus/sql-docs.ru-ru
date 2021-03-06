---
title: Просмотр моделей интеллектуального анализа данных в Visio (надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- diagram, modifying
- templates [Visio]
- shapes, data mining
- diagram
ms.assetid: 5841adea-6650-4fae-8526-26af33edbede
author: minewiskan
ms.author: owend
ms.openlocfilehash: fe6baff391f108e14a401a0d3b9dcacefa6da406
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84938145"
---
# <a name="viewing-data-mining-models-in-visio-data-mining-add-ins"></a>Просмотр моделей интеллектуального анализа данных в Visio (надстройки интеллектуального анализа данных)
  Фигуры Visio для интеллектуального анализа данных позволяют подключаться к серверу и создавать диаграммы, представляющие существующую модель интеллектуального анализа данных. Затем диаграммы можно настроить с помощью элементов управления Visio, но можно также выполнять детализацию данных, выводить некоторые данные статистики, на которой она основывается, и работать с базовой моделью.  
  
## <a name="building-a-model-diagram"></a>Создание диаграммы модели  
 При открытии файла, содержащего фигуры Visio для интеллектуального анализа данных, на панели « **фигуры** » отображаются следующие фигуры.  
  
 Если при открытии Visio фигуры интеллектуального анализа данных не отображаются, откройте файл шаблона, расположенный в папке установки.  
  
 ![DM](media/dm-stencil.gif "DM")  
  
 Для использования фигуры перетащите ее на лист. Для каждой фигуры запускается отдельный мастер, который помогает выбрать исходные данные, задать параметры для определенного типа схемы и определить заливку и другие параметры отображения.  
  
 В следующей таблице перечислены типы моделей, которые можно использовать для каждого типа диаграмм.  
  
|Фигура Visio|Поддерживаемые модели|  
|-----------------|----------------------|  
|Дерево принятия решений|Используйте эту фигуру для моделей на основе дерева принятия решений или алгоритма линейной регрессии.|  
|Сеть зависимостей|Используйте эту фигуру для моделей на основе любого из следующих алгоритмов: упрощенный алгоритм Байеса, деревья принятия решений или правила взаимосвязей.|  
|Кластер|Используйте эту фигуру для моделей, основанных на алгоритмах кластеризации.|  
  
 В зависимости от типа данных модели интеллектуального анализа данных, мастер может предлагать различные параметры. Например, столбцы, содержащие непрерывные числа отображаются иначе, чем категориальные переменные.  
  
## <a name="working-with-completed-shapes"></a>Работа с завершенными фигурами  
 После создания диаграммы вы можете использовать ее для изучения модели интеллектуального анализа данных или улучшения диаграммы для использования ее в презентациях.  
  
### <a name="visio-menus"></a>Меню Visio  
 Visio содержит разнообразные элементы управления отрисовкой, темы и контекстные меню для улучшения диаграмм.  
  
-   Используйте темы Visio для изменения цветов диаграммы.  
  
-   Изменение соединителей или макета диаграммы.  
  
### <a name="data-mining-menus"></a>Меню интеллектуального анализа данных  
 Эти панели инструментов и элементы меню предоставляются в составе настроек, которые соответствуют каждой фигуре или типу модели.  
  
-   У диаграммы каждого типа есть контекстное меню для фигуры, предоставляющее доступ к специальным параметрам. Хотя многие параметры в этом меню доступны для всех фигур Visio, некоторые из них предоставляются только для шаблонов интеллектуального анализа данных.  
  
     Например, на схеме дерева решений можно щелкнуть отдельный узел и затем развернуть дочерние узлы, чтобы упростить схему или переместить их на отдельный лист.  
  
-   Поскольку форма привязана к данным модели, можно также выполнить некоторое количество исследований при помощи диаграммы.  
  
     Фильтрация отображаемых узлов или изменение уровня дерева или глубины диаграммы.  
  
     Увеличение определенных разделов, поиск узлов, содержащих определенный атрибут, или фильтрация диаграммы зависимостей по ребрам (вероятность).  
  
## <a name="walkthroughs"></a>Пошаговые руководства  
 Примеры работы с законченной диаграммой и ее интерпретации см. в следующих разделах:  
  
 [Пошаговое руководство по диаграмме кластеров](cluster-diagram-walkthrough-data-mining-add-ins.md)  
  
 [Пошаговое руководство по диаграмме сети зависимостей](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
 [Пошаговое руководство по диаграмме дерева принятия решений](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
## <a name="see-also"></a>См. также:  
 [Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
