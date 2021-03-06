---
title: Матрица классификации (Analysis Services — интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], validating
- validating data mining models
- viewing mining accuracy
- displaying mining accuracy
- confusion matrix [data mining]
- classification matrix [Analysis Services]
- accuracy testing [data mining]
ms.assetid: 5c12f202-2ed9-41fa-bee2-0f7ab3ff058a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac1067bf817051f28c939ce5f438dd617e4a9495
ms.sourcegitcommit: 2f166e139f637d6edfb5731510d632a13205eb25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84524837"
---
# <a name="classification-matrix-analysis-services---data-mining"></a>Матрица классификации (службы Analysis Services — интеллектуальный анализ данных)
  *Матрица классификации* сортирует все варианты из модели по категориям, определяя, соответствовало ли прогнозируемое значение действительному. Затем все варианты в каждой категории пересчитываются, и полученные количества выводятся в виде матрицы. Матрица классификации — это стандартный инструмент для оценки статистических моделей, иногда ее называют *матрицей противоречий*.  
  
 Диаграмма, созданная с выбранным параметром **Матрица классификации** , сравнивает действительное значение с прогнозируемым для каждого заданного прогнозируемого варианта. Строки в матрице представляют прогнозируемые значения для модели, а в столбцах представлены действительные значения. В анализе используются категории *ложный положительный результат*, *истинный положительный результат*, *ложный отрицательный результат*и *истинный отрицательный результат*  
  
 Матрица классификации — это важный инструмент для оценки результатов прогнозирования, так как позволяет легко понять и объяснить последствия неверных прогнозов. Просматривая суммы и проценты в каждой ячейке этой матрицы, можно быстро понять, как часто предсказания модели были верны.  
  
 В этом разделе поясняется, как создать матрицу классификации и интерпретировать получаемые результаты.  
  
## <a name="understanding-the-classification-matrix"></a>Основные сведение о матрице классификации  
 Рассмотрим модель, созданную для учебника по интеллектуальному анализу данных. Модель [TM_DecisionTree] помогает создать целевую рассылку и позволит спрогнозировать, какие клиенты с наибольшей вероятностью купят велосипед. Для проверки эффективности модели используется набор данных, для которого значения атрибута результата [Bike Buyer] уже известны. Обычно используется набор проверочных данных, сохраненный со времени создания структуры интеллектуального анализа данных, которая используется для обучения модели.  
  
 Возможны два результата: "да" (существует вероятность того, что клиент купит велосипед) и "нет" (скорее всего, клиент велосипед не купит). Таким образом, результирующая матрица классификации относительно проста.  
  
## <a name="interpreting-the-results"></a>Интерпретация результатов  
 В следующей таблице показана матрица классификации для модели TM_DecisionTree. Помните, что для этого прогнозируемого атрибута значение 0 означает «нет», а значение 1 — «да».  
  
|Прогноз|0 (фактическое значение)|1 (фактическое значение)|  
|---------------|------------------|------------------|  
|0|362|144|  
|1|121|373|  
  
 Первая ячейка результата, которая содержит значение 362, указывает количество *истинных положительных результатов* для значения 0. Поскольку 0 означает, что клиент не приобрел велосипед, этот статистический показатель сообщает, что модель спрогнозировала правильное значение для клиентов, не купивших велосипед, в 362 случаях.  
  
 Ячейка, которая расположена непосредственно ниже и содержит значение 121, указывает число *ложных положительных результатов*, то есть количество раз, когда ожидалось, что клиент приобретет велосипед, но в действительности покупка не состоялась.  
  
 Ячейка, которая содержит значение 144, указывает количество *ложных положительных результатов* для значения 1. Поскольку 1 означает, что клиент приобрел велосипед, этот статистический показатель сообщает, что модель в 144 случаях спрогнозировала, что клиент не приобретет велосипед, а в действительности покупка состоялась.  
  
 Наконец, ячейка результата, которая содержит значение 373, указывает количество истинных положительных результатов для целевого значения 1. Другими словами, в 373 случаях модель правильно предсказала, что некто приобретет велосипед.  
  
 Сложив значения в ячейках, расположенных на одной диагонали, можно определить общую точность модели. Одна диагональ позволяет определить общее число точных прогнозов, а вторая — общее число ошибочных прогнозов.  
  
### <a name="using-multiple-predictable-values"></a>Использование нескольких прогнозируемых значений  
 Вариант [Bike Buyer] особенно просто интерпретировать, поскольку для него возможны только два значения. Если прогнозируемый атрибут имеет несколько возможных значений, матрица классификации добавляет новый столбец для каждого возможного фактического значения и затем подсчитывает число совпадений для каждого прогнозируемого значения. В следующей таблице показаны результаты для другой модели, когда возможны три значения (0, 1, 2).  
  
|Прогноз|0 (фактическое значение)|1 (фактическое значение)|2 (действительное значение)|  
|---------------|------------------|------------------|------------------|  
|0|111|3|5|  
|1|2|123|17|  
|2|19|0|20|  
  
 Хотя добавление столбцов делает отчет более сложным, дополнительные данные могут оказаться очень полезными, когда необходимо оценить совокупную стоимость неправильных прогнозов. Чтобы вычислить суммы по диагоналям или сравнить результаты для различных сочетаний строк, можно нажать кнопку **Копировать** на вкладке **Матрица классификации** и вставить отчет в Excel. Кроме того, можно использовать клиент (например, клиент интеллектуального анализа данных для Excel), который поддерживает [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздние версии, для создания прямо в Excel классификационного отчета, включающего как численные, так и процентные результаты. Дополнительные сведения см. в разделе [Интеллектуальный анализ в SQL Server](https://go.microsoft.com/fwlink/?LinkID=77733).  
  
## <a name="restrictions-on-the-classification-matrix"></a>Ограничения для матрицы классификации  
 Матрицу классификации можно использовать только с дискретными прогнозируемыми атрибутами.  
  
 Хотя при выборе моделей на вкладке **Выбор входа** конструктора **Диаграмма точности интеллектуального анализа** можно добавить несколько моделей, на вкладке **Матрица классификации** будет показана отдельная матрица для каждой модели.  
  
## <a name="related-content"></a>См. также  
 В следующих разделах содержатся дополнительные сведения о том, как создать и использовать матрицу классификации и другие диаграммы.  
  
|Разделы|Ссылки|  
|------------|-----------|  
|Объясняет, как создать диаграмму точности прогнозов для модели целевой рассылки.|[Учебник по основам интеллектуального анализа данных](../../tutorials/basic-data-mining-tutorial.md)<br /><br /> [Проверка точности с помощью диаграмм точности прогнозов (учебник интеллектуального анализа данных — начальный уровень)](../../tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)|  
|Объясняет типы соответствующих диаграмм.|[Диаграмма точности прогнозов (службы Analysis Services — интеллектуальный анализ данных)](lift-chart-analysis-services-data-mining.md)<br /><br /> [Диаграмма роста прибыли (службы Analysis Services — интеллектуальный анализ данных)](profit-chart-analysis-services-data-mining.md)<br /><br /> [Точечная диаграмма (службы Analysis Services — интеллектуальный анализ данных)](scatter-plot-analysis-services-data-mining.md)|  
|Описывает использование перекрестной проверки для моделей интеллектуального анализа данных и структур интеллектуального анализа данных.|[Перекрестная проверка (службы Analysis Services — интеллектуальный анализ данных)](cross-validation-analysis-services-data-mining.md)|  
|Описывает шаги для создания диаграммы точности прогнозов и других диаграмм точности.|[Задачи и решения по тестированию и проверке (интеллектуальный анализ данных)](testing-and-validation-tasks-and-how-tos-data-mining.md)|  
  
## <a name="see-also"></a>См. также:  
 [Тестирование и проверка (интеллектуальный анализ данных)](testing-and-validation-data-mining.md)  
  
  
