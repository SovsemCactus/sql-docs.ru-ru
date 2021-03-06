---
title: Алгоритм кластеризации (Майкрософт) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation algorithms [Analysis Services]
- nearest neighbor [Data Mining]
- clustering [Data Mining]
- clusters [Analysis Services]
- relationships [Analysis Services], clusters
- algorithms [data mining]
- classification algorithms [Analysis Services]
- datasets [Analysis Services]
- clustering algorithms [Analysis Services]
ms.assetid: 92a1e67e-f46e-4960-99b2-4d20f6192fbd
author: minewiskan
ms.author: owend
ms.openlocfilehash: dc1a06de710276d5f8b60a44d0f1259026a9a973
ms.sourcegitcommit: 2f166e139f637d6edfb5731510d632a13205eb25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84522138"
---
# <a name="microsoft-clustering-algorithm"></a>Алгоритм кластеризации (Майкрософт)
  Алгоритм кластеризации [!INCLUDE[msCoName](../../includes/msconame-md.md)] представляет собой алгоритм сегментации, предоставляемый службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Алгоритм использует итерационные методы для группировки вариантов в наборы данных в кластерах, содержащих подобные характеристики. Такие группирования полезно использовать для просмотра данных, выявления в них аномалий и создания прогнозов.

 Модели кластеризации определяют связи в наборе данных, который невозможно логически получить с помощью случайного наблюдения. Например, можно логически отличить, что люди, добирающиеся на работу на велосипеде, не обязательно живут далеко от работы. Алгоритм может найти другие не очевидные характеристики велосипедистов. На следующей диаграмме кластер А соответствует людям, добирающимся до работы на машине, а кластер Б — людям, добирающимся до работы на велосипеде.

 ![Шаблон кластера тенденций местного сообщения](../media/clustering-example.gif "Шаблон кластера тенденций местного сообщения")

 Алгоритм кластеризации отличается от других алгоритмов интеллектуального анализа данных, например алгоритма дерева принятия решений [!INCLUDE[msCoName](../../includes/msconame-md.md)] , в котором не требуется назначать прогнозируемый столбец, необходимый для создания модели кластеризации. Алгоритм кластеризации обучает модель строго на основе связей, существующих в данных и на основе кластеров, идентифицированных алгоритмом.

## <a name="example"></a>Пример
 Рассмотрим группу людей, имеющих сходные демографические данные и покупающих подобные товары в компании [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] . Эта группа людей представляет собой кластер данных. В базе данных может существовать несколько таких кластеров. Просматривая столбцы, образующие кластер, можно более точно просмотреть, как записи в наборе данных связаны друг с другом.

## <a name="how-the-algorithm-works"></a>Принцип работы алгоритма
 Алгоритм кластеризации [!INCLUDE[msCoName](../../includes/msconame-md.md)] сначала определяет связи в наборе данных и формирует ряд кластеров на основе этих связей. Точечная диаграмма является хорошим способом визуально представить, как алгоритм группирует данные (см. следующую диаграмму). Точечная диаграмма представляет все варианты в наборе данных, и каждый вариант является точкой на диаграмме. Группа кластеров указана на диаграмме точками и показывает связи, идентифицированные алгоритмом.

 ![Точечная диаграмма вариантов набора данных](../media/clustering-plot.gif "Точечная диаграмма вариантов набора данных")

 После первого определения кластеров алгоритм вычисляет, как кластеры представляют группирование точек, а затем пытается повторно определить группирования, чтобы создать кластеры, которые лучше представляют данные. Алгоритм последовательно выполняет этот процесс до тех пор, пока улучшить результаты, определяя кластеры, будет невозможно.

 Можно настраивать работу данного алгоритма, выбирая конкретный метод объединения в кластеры, ограничивая максимальное количество кластеров или изменяя размер несущего множества, необходимый для создания кластера. Дополнительные сведения см. в разделе [Технический справочник по алгоритму кластеризации (Майкрософт)](microsoft-clustering-algorithm-technical-reference.md).

## <a name="data-required-for-clustering-models"></a>Данные, необходимые для моделей кластеризации
 При подготовке данных, предназначенных для использования в обучении модели кластеризации, следует учитывать требования к конкретному алгоритму, в том числе к объему необходимых данных, и то, как эти данные используются.

 Требования для модели кластеризации являются следующими.

-   **Единичный ключевой столбец** Каждая модель должна содержать один числовой или текстовый столбец, который уникальным образом определяет каждую запись. Применение составных ключей не допускается.

-   **Входные столбцы** Каждая модель должна содержать по меньшей мере один входной столбец, включающий значения, которые используются для формирования кластеров. Ограничения на количество входных столбцов не налагаются, но, в зависимости от количества значений в каждом столбце, введение дополнительных столбцов может привести к увеличению времени на обучение модели.

-   **Необязательный прогнозируемый столбец** Этому алгоритму не требуется прогнозируемый столбец для формирования модели, но предусмотрена возможность добавления прогнозируемого столбца с данными почти любого типа. Значения в прогнозируемом столбце могут рассматриваться как входные по отношению к модели кластеризации, или может быть указано, что эти данные используются только для прогноза. Например, если требуется предсказать доход заказчика путем кластеризации по таким демографическим показателям, как регион или возраст, то можно задать доход как `PredictOnly` и ввести все остальные столбцы, например с данными о регионе или возрасте, в качестве входных данных.

 Дополнительные сведения о типах содержимого и типах данных, поддерживаемых моделями кластеризации, см. в подразделе "Требования" раздела [Технический справочник по алгоритму кластеризации (Майкрософт)](microsoft-clustering-algorithm-technical-reference.md).

## <a name="viewing-a-clustering-model"></a>Просмотр модели кластеризации
 Чтобы исследовать модель, можно использовать **Средство просмотра кластеров (Майкрософт)**. При просмотре модели кластеризации в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] кластеры отображаются на диаграмме, которая показывает связи между кластерами, а также содержит подробный профиль каждого кластера, список атрибутов, по которым различаются кластеры, и характеристики всего набора данных для обучения. Дополнительные сведения см. в разделе [Просмотр модели с помощью средства просмотра кластеров (Майкрософт)](browse-a-model-using-the-microsoft-cluster-viewer.md).

 Чтобы получить более подробные сведения, можно просмотреть модель с помощью [средства просмотра деревьев содержимого общего вида (Майкрософт)](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md). Содержимое, сохраняемое для модели, включает распределение всех значений в каждом узле, вероятность каждого кластера и другую информацию. Дополнительные сведения см. в разделе [Содержимое моделей интеллектуального анализа данных для моделей кластеризации (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-for-clustering-models-analysis-services-data-mining.md).

## <a name="creating-predictions"></a>Создание прогнозов
 После обучения модели результаты хранятся в виде набора закономерностей, которые можно исследовать или делать на их основе прогнозы.

 Предусмотрена возможность создавать запросы, возвращающие прогнозы того, соответствуют ли новые данные обнаруженным кластерам, или предоставляющие описательные статистические данные о кластерах.

 Дополнительные сведения о создании запросов к модели интеллектуального анализа данных см. в разделе [Запросы интеллектуального анализа данных](data-mining-queries.md). Примеры использования запросов с моделью кластеризации см. в разделе [Примеры запросов к модели кластеризации](clustering-model-query-examples.md).

## <a name="remarks"></a>Комментарии

-   Поддерживается использование языка разметки прогнозирующих моделей (PMML) для создания моделей интеллектуального анализа данных.

-   Поддерживается детализация.

-   Поддерживается использование моделей интеллектуального анализа OLAP и создание измерений интеллектуального анализа данных.

## <a name="see-also"></a>См. также:
 [Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-algorithms-analysis-services-data-mining.md) содержимое модели интеллектуального анализа с [алгоритмом кластеризации Microsoft](microsoft-clustering-algorithm-technical-reference.md) [для моделей кластеризации &#40;Analysis Services — примеры запросов интеллектуального анализа данных&#41;](mining-model-content-for-clustering-models-analysis-services-data-mining.md) [модели кластеризации](clustering-model-query-examples.md)


