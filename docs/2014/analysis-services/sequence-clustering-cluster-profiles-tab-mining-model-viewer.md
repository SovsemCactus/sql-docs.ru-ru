---
title: Вкладка «Профили кластера кластеризации последовательностей» (средство просмотра моделей интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.profiles.f1
ms.assetid: 44230895-0a42-4032-8d6c-0cdb8a2dbb8c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7b7aff4d6a7f4f685fe589e2fb141848296bb82b
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84940704"
---
# <a name="sequence-clustering-cluster-profiles-tab-mining-model-viewer"></a>Вкладка «Профили кластеров кластеризации последовательностей» (средство просмотра моделей интеллектуального анализа данных)
  На вкладке **Профили кластера** в **средстве просмотра кластеризации последовательностей (Майкрософт)** содержатся представления последовательностей с цветовой кодировкой, включенных в каждый кластер.  
  
 Используйте представление модели кластеризации последовательностей, чтобы быстро просмотреть способы группирования последовательностей, обнаруженных моделью. Можно с одного взгляда выяснить, сколько последовательностей являются длинными и сколько — короткими. Можно также щелкнуть кластер для отображения **Легенды интеллектуального анализа данных** , которая позволит точно узнать, какие состояния представляют цвета в каждой последовательности.  
  
 **Дополнительные сведения:**  [Алгоритм кластеризации последовательностей (Майкрософт)](data-mining/microsoft-sequence-clustering-algorithm.md), [Просмотр модели с помощью средства просмотра кластеризации последовательностей (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)  
  
## <a name="options"></a>Варианты  
 **Обновить содержимое средства просмотра**  
 Перезагрузить модель интеллектуального анализа данных в средстве просмотра.  
  
 **Модель интеллектуального анализа данных**  
 Выберите для просмотра модель интеллектуального анализа данных, содержащуюся в текущей структуре интеллектуального анализа данных. Модель интеллектуального анализа данных открывается в связанном средстве просмотра.  
  
 **Зритель**  
 Выберите средство просмотра для обзора выбранной модели интеллектуального анализа данных. Можно использовать пользовательское средство просмотра или **средство просмотра деревьев содержимого общего вида (Майкрософт)**. Также можно использовать подключаемые модули просмотра, если они доступны.  
  
 **Показать условные обозначения**  
 Выберите данный параметр для отображения условных обозначений, показывающих связь между цветами в профилях кластера и текстовыми значениями состояний.  
  
 **Столбцы гистограммы**  
 Используйте этот параметр, чтобы изменить количество цветных столбцов на гистограмме. Если доступно больше столбцов, чем выбрано для отображения, наиболее важные столбцы остаются, а оставшиеся группируются в **Другие**.  
  
 **Атрибуты** и **Профили кластера**  
 В этом разделе диаграммы перечисляют кластеры последовательностей, обнаруженные в модели.  
  
 Каждый кластер последовательностей отображается с использованием нескольких состояний, выбранных в параметре **Столбцы гистограмм**.  
  
 Два набора гистограмм отображаются для каждого кластера в модели, каждый из них в отдельной строке диаграммы:  
  
-   ** \<attribute name> . Samples**: гистограммы в этой строке показывают последовательности элементов, которые являются репрезентативными для каждого кластера. Для расширений интеллектуального анализа данных — это образцы вариантов для каждого кластера.  
  
-   **\<attribute name>**: Гистограммы в этой строке описывают все элементы, содержащиеся в кластере, и их общее распределение. Щелкните гистограмму, когда отображается **Легенда интеллектуального анализа данных** , чтобы увидеть числовые значения каждого  
  
 **Состояния**  
 Это необязательный столбец диаграммы, он может быть показан или удален путем выбора параметра **Показать условные обозначения** . Столбец **Состояния** содержит указания относительно цветов, которые представляют конкретные состояния в соответствующей гистограмме кластеров.  
  
## <a name="see-also"></a>См. также:  
 [Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Алгоритм кластеризации последовательностей (Майкрософт)](data-mining/microsoft-sequence-clustering-algorithm.md)   
 [Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md)   
 [Средства просмотра моделей интеллектуального анализа данных](data-mining/data-mining-model-viewers.md)   
 [Просмотр модели с помощью средства просмотра кластеризации последовательностей (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)  
  
  
