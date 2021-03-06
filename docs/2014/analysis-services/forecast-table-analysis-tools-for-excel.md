---
title: Прогноз (средства анализа таблиц для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- forecasting
- mining model, time series
- time series [data mining]
ms.assetid: 22bb0b5e-78f5-484e-883d-2b5985a12749
author: minewiskan
ms.author: owend
ms.openlocfilehash: a08cdf759ad3accd1f3c1405cefff9cde6b5319f
ms.sourcegitcommit: f0772f614482e0b3cde3609e178689ce62ca3a19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84544496"
---
# <a name="forecast-table-analysis-tools-for-excel"></a>Прогноз (средства анализа таблиц для Excel)
  ![Кнопка «Прогноз» на ленте «Средства анализа таблиц»](media/tat-forecast.gif "Кнопка «Прогноз» на ленте «Средства анализа таблиц»")  
  
 Средство **прогнозирования** позволяет создавать прогнозы на основе данных в таблице данных Excel или другом источнике данных, а также при необходимости просматривать вероятности, связанные с каждым прогнозируемым значением. Например, если данные содержат столбец даты и столбец, показывающий объем продаж по каждому дню месяца, можно прогнозировать объем продаж на будущие дни. Также можно указать количество выполняемых прогнозов. Например, пять дней или тридцать.  
  
 После завершения средства новые прогнозы добавятся в конец таблицы источника данных, а новые значения будут выделены цветом. Новые значения рядов времени не добавлены; это позволяет сначала предварительно просмотреть прогнозы.  
  
 Средство также создает новый лист с именем « **отчет о прогнозировании**». Этот лист сообщает об успешности создания прогноза мастером. Новый лист также содержит линейную диаграмму, показывающую тренды предыстории.  
  
 При расширении ряда времени для включения новых прогнозов прогнозируемые значения добавляются в линейную диаграмму. Значения с предысторией отображаются сплошной линией, а прогнозы — точечной.  
  
## <a name="using-the-forecast-tool"></a>Использование средства «Прогноз»  
  
1.  Откройте таблицу Excel, которая содержит прогнозируемые числовые данные.  
  
2.  На вкладке **анализ** щелкните **Прогноз** .  
  
3.  Укажите столбцы для прогноза. Средство автоматически выбирает столбцы в данных с прогнозируемым типом данных, то есть непрерывными числовыми данными. Может оказаться, что применение этого средства не привело к выбору некоторых столбцов, которые содержат непрерывные числовые данные, если эти столбцы включают много значений NULL или нулевых значений, поскольку недостающие данные могут повлиять на результаты. В этом случае данные можно исправить с помощью средства [переразметка &#40;SQL Server надстройки интеллектуального анализа данных&#41;](relabel-sql-server-data-mining-add-ins.md) средстве.  
  
4.  Укажите столбец, содержащий дату, время или другой идентификатор последовательности. При выборе параметра **\<no time stamp>** средство создаст ряд, основанный на последовательности строк в исходных данных.  
  
5.  Укажите количество выполняемых прогнозов.  
  
6.  Дополнительно можно предоставить алгоритму подсказку о том, будут ли данные повторяться еженедельно, ежемесячно или с иной периодичностью. Если данные не соответствуют ни одному из заданных шаблонов или отсутствуют какие бы то ни было закономерности, выберите, **\<detect automatically>** чтобы средство обнаружило повторяющиеся периоды времени.  
  
7.  Мастер добавит прогнозы в таблицу источника и создаст отчет о прогнозе на новом листе.  
  
8.  Для добавления новых значений в диаграмму прогнозирования расширьте временной ряд, чтобы включить спрогнозированные значения.  
  
### <a name="requirements"></a>Требования  
 Столбец для прогнозирования должен содержать непрерывные числовые данные, например данные типа валюты или другого числового типа.  
  
 По возможности данные должны также включать столбец, содержащий ряд времени или даты. Вместо данных даты и времени можно использовать числовые ряды (1, 2, 3....). Однако значения в столбце последовательности должны быть уникальны. Если средство **прогнозирования** находит дублирующиеся значения в столбце ряда, возникает ошибка.  
  
 Вы не можете предсказать дату с помощью средства **прогнозирования** . Хотя ошибка может и не произойти, данный алгоритм не предназначен для использования дат в качестве прогнозируемых значений.  
  
### <a name="understanding-time-stamps"></a>Основные сведения о временных метках  
 Необходимо указать столбец для использования в качестве *отметки времени*. Временная метка служит для двух целей. Во-первых, однозначно определяет значение во временном ряду. Например, если рассматриваются данные о продажах за день, должно существовать только одно значение о продажах за каждый день. В качестве временной метки может использоваться календарная дата. Во-вторых, столбец временной метки указывает, какая единица измерения применяется для выполнения прогнозов. Если отслеживаются результаты продажи за день, в прогнозах в качестве единиц измерения также должны использоваться дни.  
  
 Если данные не имеют столбца даты или времени, данное средство автоматически создаст временный ключевой столбец с именем _RowIndex. Этот ключ будет основан на порядке строк в наборе данных.  
  
 При указании количества прогнозов необходимо ввести целое число, которое указывает количество шагов. Величина этих шагов зависит от единиц измерения, используемых в исходных данных для ряда времени и дат. Если данные содержат результаты продаж за месяц, прогноз будет выполнен для ряда месяцев. Выбранную единицу измерения времени нельзя изменить до тех пор, пока не изменится источник данных.  
  
### <a name="understanding-periodicity"></a>Основные сведения о периодичности  
 В основе прогноза лежит выявление закономерностей, повторяющихся в течение определенного периода времени. Поэтому в алгоритме временных рядов (Майкрософт) выполняются вычисления, чтобы определить периоды времени, имеющие наиболее ярко выраженные закономерности. *Периодичность* относится к этим периодам времени.  
  
 Временной ряд может содержать много потенциальных закономерностей. Если есть уверенность в том, что какие-то конкретные данные содержат определенную закономерность, можно попытаться улучшить качество прогноза путем предоставления подсказки алгоритму.  
  
 Например, если предполагается, что данные повторяются еженедельно, можно выбрать значение «Еженедельно», чтобы указать, что алгоритм должен искать еженедельные закономерности. Но, если какие-либо ярко выраженные еженедельные закономерности не будут найдены, алгоритм не будет учитывать подсказку.  
  
## <a name="understanding-the-forecasting-report"></a>Основные сведения о прогнозирующем отчете  
 На этой диаграмме исторические данные из таблицы данных отображаются темной линией. Прогнозируемые значения отображаются пунктирными линиями. Можно щелкнуть по точке на линии для просмотра прогнозируемого значения.  
  
> [!NOTE]  
>  Если на оси времени для прогнозируемых значений на диаграмме не отображаются метки, откройте лист, содержащий прогнозируемые значения, и используйте функцию **Fill, Series** в Excel, чтобы расширить столбец временных меток, чтобы включить прогнозируемые значения.  
  
 Иногда прогнозу может не хватать необходимого количества временных срезов. Обычно это означает, что алгоритму недостаточно данных для прогноза на более продолжительное время. Средство **прогнозирования** будет выполнять только прогнозы, соответствующие минимальному пороговому значению вероятности.  
  
## <a name="related-tools"></a>Дополнительные средства  
 Клиент интеллектуального анализа данных для Excel, который является отдельной надстройкой, обеспечивающей расширенную функциональность интеллектуального анализа данных, также содержит мастер прогноза.  
  
 Как средство **прогнозирования** (в средствах анализа таблиц для Excel), так и мастер **прогнозов** (в клиенте интеллектуального анализа данных для Excel) используют [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритм временных рядов.  
  
-   Средство **прогнозирования** проще в использовании, так как оно автоматически настраивает алгоритм для использования параметров, наиболее подходящих для ваших данных.  
  
-   Мастер **прогнозов** в клиенте интеллектуального анализа данных для Excel предоставляет возможность настройки параметров.  
  
 Дополнительные сведения о мастере **прогнозов** см. в разделе [мастер прогнозов &#40;надстройки интеллектуального анализа данных для&#41;Excel ](forecast-wizard-data-mining-add-ins-for-excel.md). Дополнительные сведения об алгоритме прогнозирования см. в разделе «Алгоритм временных рядов (Майкрософт)» электронной документации по [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>См. также:  
 [Средства анализа таблиц для Excel](table-analysis-tools-for-excel.md)  
  
  
