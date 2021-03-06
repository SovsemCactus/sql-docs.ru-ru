---
title: Выбор данных для интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content type [data mining]
- nested tables
- key [data mining]
- continuous values
- key sequence [data mining]
- table data type
- key time [data mining]
- discrete values
- discretized
ms.assetid: 7c72d80e-913c-4bbe-b258-444294a78838
author: minewiskan
ms.author: owend
ms.openlocfilehash: 589a1f64a3bed5455f8004e51f6cddf84e83fec5
ms.sourcegitcommit: 2f166e139f637d6edfb5731510d632a13205eb25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84527590"
---
# <a name="choosing-data-for-data-mining"></a>Выбор данных для интеллектуального анализа данных
  При запуске интеллектуального анализа данных можно задать вопрос «какой объем данных требуется?». или "есть ли особые требования, о которых следует помнить при очистке или форматировании данных?"  
  
 В частности, пользователи, ранее не знакомые с интеллектуальным анализом данных, часто сталкиваются с проблемами в Excel, например с необходимостью согласованного форматирования данных в столбцах, очисткой отсутствующих значений или группированием чисел. В этом разделе также приведены требования к данным для определенных типов моделей.  
  
 [Выбор данных](#bkmk_ChoosingData)  
  
 [Распространенные проблемы с данными](#bkmk_CommonDataProblems)  
  
 [Прочие требования к данным](#bkmk_OtherRequirements)  
  
##  <a name="choosing-data"></a><a name="bkmk_ChoosingData"></a>Выбор данных  
 Выбор данных, используемых для анализа, возможно, является наиболее важной частью процесса интеллектуального анализа данных — даже более важной, чем выбор алгоритма. Это связано с тем, что интеллектуальный анализ основывается не на гипотезах, а на данных. Вместо того чтобы выбрать и проверить переменные заранее, как это делается в традиционных статистических моделях, интеллектуальный анализ может получать данные и открывать новые связи (или совсем не обнаружить никаких закономерностей). Качество и объем данных могут оказать значительное влияние на результат.  
  
 В целом придерживайтесь следующих правил.  
  
-   Получите как можно более чистые данные.  
  
-   Выполните профилирование данных перед использованием любых моделей. Необходимо понимать, с какими данными вы работаете, чтобы получить из них информацию. Как минимум:  
  
    1.  Используйте инструменты в надстройках для поиска минимальных и максимальных значений, наиболее распространенных и средних значений.  
  
    2.  Заполните все отсутствующие значения. Надстройки (а также некоторые алгоритмы) реализуют средства для ввода отсутствующих значений.  
  
    3.  Исправьте недопустимые данные, если это возможно. Проекты интеллектуального анализа данных часто используются в качестве стимула для новых по обработке данных.  
  
-   Попробуйте создать тестовую модель и найти проблемы с данными с ее помощью. Проверяя результаты, вы можете обнаружить, например, что прогнозы продаж основаны на аномальных данных из-за ошибки конвертации валют.  
  
-   Попробуйте преобразовать данные в различные форматы или сегментировать значения. Шаблоны часто выявляются после преобразования данных.  
  
     Например, на уровень обслуживания в центре обработки вызовов может повлиять день недели, чего бы вы не увидели, если бы использовали только значения даты и времени. Прогнозы могут быть лучше, если создать их на основе 10-дневных циклов, а не недельных или дневных единиц.  
  
-   Поместите числа в соответствующие сегменты, чтобы уменьшить число возможных значений для анализа.  
  
-   Создайте несколько версий данных и постройте несколько моделей.  
  
 Дополнительные советы по выбору, изменению и просмотру данных см. в разделе [Контрольный список подготовки к интеллектуальному анализу данных](checklist-of-preparation-for-data-mining.md).  
  
### <a name="how-much-data-do-i-need"></a>Сколько данных мне нужно?  
 Старайтесь придерживаться следующего правила: для самых простых типов моделей и сценариев должно иметься не менее 50–100 строк данных. Например, если осуществляется прогноз одного атрибута с помощью модели упрощенного алгоритма Байеса и набор данных правильного формата, то можно будет получить довольно точные прогнозы с использованием 50–100 строк данных.  
  
 Для моделей взаимосвязей обычно требуется гораздо больше данных — тысячные строки могут оказаться недостаточными при анализе большого количества атрибутов, например связей между продуктами. Если набор данных слишком велик или мал, иногда можно улучшить результаты с помощью сжатия строк по категориям. Например, вместо того чтобы анализировать взаимосвязи между отдельными продуктами, можно классифицировать продукты по категориям.  
  
 Если набор данных имеет разумный размер, сосредоточьтесь на качестве данных, а не на добавлении новой информации. В какой-то момент, когда будут найдены все статистически действительные шаблоны, добавление данных перестанет повышать качество шаблонов. И наоборот, по мере добавления данных иногда могут появиться случайные корреляции.  
  
### <a name="discrete-vs-continuous-numbers"></a>Дискретные Непрерывные числа  
 *Дискретный* столбец содержит конечное количество значений. Например, текстовые данные всегда рассматривается как дискретные значения.  
  
 Существуют некоторые важные атрибуты для дискретизации значений. Например, если числа обрабатываются как дискретные, то их порядок не учитывается и нельзя получить среднее или суммарное значение показателей. Междугородние телефонные коды — хороший пример дискретных числовых данных, которые никогда не используются для выполнения математических операций.  
  
 Дискретные значения иногда называют категориальными, так как по ним можно сгруппировать набор данных. Для чисел, расположенных в бесконечном ряду, это невозможно.  
  
 Числа также можно обрабатывать как дискретные, если значения четко различаются, а дробные значения недопустимы или бесполезны.  
  
 *Непрерывные* числовые данные могут содержать бесконечное количество дробных значений. Примером непрерывного столбца является столбец доходов. Если указать, что столбец является числовым, каждое значение в нем должно быть числовым, кроме NULL. Обратите внимание, что в Excel можно учитывать метки времени и любое другое представление даты и времени, которое можно преобразовать в тип данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .  
  
 **Преобразование чисел в категориальные переменные**  
  
 Если столбец содержит числа, это не обязательно означает, что их необходимо обрабатывать как непрерывные числа. *Дискретизация* предоставляет множество преимуществ при анализе. Одно из них — уменьшение проблемной области. Кроме того, числа иногда не подходят два выражения результата.  
  
 Например, количество детей в семье может считаться непрерывным или дискретным значением. Так как в семье не может быть 2,5 ребенка, а семьи с 3 или более детьми могут сильно отличаться от семей с 2 детьми, можно получить лучшие результаты, обрабатывая это число как категорию. Но если вы создаете регрессионную модель или вам требуется иным образом получить среднее значение (например, 1,357 ребенка на семью), то необходимо использовать непрерывный тип числовых данных.  
  
 Нельзя создать модель интеллектуального анализа данных с непрерывными данными и затем обрабатывать столбец как дискретный. Эти два набора данных необходимо обрабатывать по-разному, при этом делать это на сервере в виде отдельных структур интеллектуального анализа данных. Если вы не уверены в том, как правильно обрабатывать данные, необходимо создать отдельные модели, чтобы обрабатывать сведения по-разному. В любом случае это хороший способ получения другой точки зрения на данные и, возможно, других результатов.  
  
 **Преобразование чисел в текст**  
  
 Очень часто значения, которые должны быть дискретными, например «Мужчина» и «Женщина», представлены в виде числовых данных с помощью меток 1 и 2. Как правило, такое кодирование выполняется для упрощения ввода данных или уменьшения использования пространства в базе данных, но само это кодирование может привести к возникновению неоднозначности при толковании характера или смысла значений. Кроме того, такие дискретные значения хранятся в виде чисел, поэтому при перемещении данных из одного приложения в другое могут возникнуть ошибки преобразования типов данных, а к самим значениям могут применяться вычисления или другие способы обработки, предусматривающие их трактовку как непрерывных. Чтобы предотвратить возникновение подобных проблем, до выполнения интеллектуального анализа данных можно преобразовать числовые метки обратно в дискретные текстовые метки.  
  
 **Группирование чисел**  
  
 Хотя все числа в принципе бесконечны и, следовательно, являются непрерывными, при моделировании информации может быть более эффективно *дискретизировать* допустимые значения или сделать их *двоичными* .  
  
 Выполнить сегментирование данных можно различными способами.  
  
-   Укажите конечное число контейнеров и позвольте алгоритму отсортировать значения по контейнерам.  
  
-   Можно предварительно сгруппировать их вручную, создав набор группирований, которые имеют определенное бизнес-значение или с которыми легче работать. При таком подходе часто теряется реальное распределение значений, но диапазоны более удобны для пользователей.  
  
-   Можно позволить алгоритму определить оптимальное количество контейнеров и распределение значений. Это метод по умолчанию для большинства инструментов, но настройки по умолчанию можно изменить в мастерах на панели инструментов **Интеллектуальный анализ данных** .  
  
-   Можно аппроксимировать значения к центральному среднему или репрезентативному значению.  
  
##  <a name="common-data-problems"></a><a name="bkmk_CommonDataProblems"></a>Распространенные проблемы с данными  
  
### <a name="excel-number-formats"></a>Числовые форматы Excel  
 Excel — это простое средство для использования, так как оно терпим отношению — вы можете разместить практически любой тип данных в любом месте! Однако, прежде чем начать поиск шаблонов и анализ корреляций, нужно определить структуру или некоторые ограничения данных.  
  
 По умолчанию при импорте числовых данных в [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel числа сохраняются в десятичном формате с двумя знаками после запятой. Если этот числовой формат не подходит, можно изменить его на другой или изменить количество десятичных разрядов.  
  
 Один вариант — использовать средство [Переразметка](relabel-sql-server-data-mining-add-ins.md) для изменения способа отображения и группирования чисел.  
  
 Однако, если данные слишком сложны для обработки с помощью средства **Переразметка** , вместо этого можно применить числовые функции Excel, чтобы преобразовать данные в дискретный диапазон, сохранить результат в отдельный столбец, а затем воспользоваться дискретизированным столбцом для классификации.  
  
 Например, если при анализе результатов скачек потребуется сгруппировать участников по финишному времени в минутах, можно провести округление до ближайшей минуты и сохранить это округленное значение в новом столбце. Кроме того, при помощи функции `MINUTE` можно извлечь значение минут, а затем сохранить его в новом столбце для использования в анализе.  
  
### <a name="discretizing-numbers-and-dates-in-excel"></a>Дискретизация чисел и дат в Excel  
 По умолчанию числовые данные в Excel имеют тип `Double`. Дата и время хранятся в числовом формате. Если необходимо дискретизировать числа или даты для интеллектуального анализа данных, то следует добавить новые столбцы перед тем, как создавать модель интеллектуального анализа данных, либо заранее преобразовать значения даты и времени в другой формат.  
  
### <a name="scientific-number-formats"></a>Научные числовые форматы  
 Средства интеллектуального анализа данных часто выводят вероятности в экспоненциальном формате для представления чисел, являющихся очень большими или очень маленькими. Если пользователь незнаком с экспоненциальным форматом, данные числа можно отобразить в другом формате, изменив форматирование ячеек.  
  
##### <a name="to-change-scientific-notation-to-a-decimal-numeric-format"></a>Изменение экспоненциального формата на десятичный числовой формат  
  
1.  Выделите в таблице Excel столбец или ячейку, содержащую число в экспоненциальном формате.  
  
2.  Щелкните ее правой кнопкой мыши и в контекстном меню выберите пункт **Формат ячейки** .  
  
3.  В списке **Категория** выберите **Число**.  
  
4.  Увеличьте число десятичных разрядов. Вероятность, представляемая в экспоненциальном формате, обычно является крайне малой.  
  
     Изменяется только отображение числа, но не базовое значение.  
  
### <a name="working-with-dates-and-times"></a>Работа со значениями даты и времени  
 Если в таблице Excel имеются даты и столбец с ними используется в качестве входных данных или для прогноза, можно получить непредвиденные результаты, зависящие от способа форматирования данных даты или времени. Например, если при использовании средств **Поиск категорий** или **Классификация** включить столбец, содержащий даты, даты разбиваются на категории, представленные как числа с множеством десятичных разрядов. Это не ошибка, это точное представление базовых данных. Алгоритм интеллектуального анализа данных работает с базовым форматом хранения, а не с форматом отображения.  
  
 Если возникли затруднения в работе с датами и необходимо проанализировать их с помощью таких очевидных группирований, как месяц или день, функции DATE в Excel позволяют получить год, месяц или день в виде отдельного столбца, а затем использовать этот столбец для классификации.  
  
##  <a name="other-data-requirements"></a><a name="bkmk_OtherRequirements"></a>Другие требования к данным  
  
### <a name="requirements-by-algorithm-type"></a>Требования по типу алгоритма  
 Некоторым алгоритмам, используемым в надстройках, для создания модели требуются определенные типы данных или содержимого.  
  
 **Модели упрощенного алгоритма Байеса**  
  
-   Упрощенный алгоритм Байеса [!INCLUDE[msCoName](../includes/msconame-md.md)] не использует непрерывные столбцы в качестве входных данных. Это значит, что нужно сегментировать числа или, если значений достаточно, обработать их как дискретные.  
  
-   Этот тип модели также не может прогнозировать непрерывные значения. Поэтому для прогнозирования непрерывного числа, например дохода, сначала сегментируйте значения в значимых диапазонах. Если вы не уверены, какие диапазоны вам подходят, можно использовать алгоритм кластеризации, чтобы определить группы чисел в данных.  
  
-   При использовании мастера на основе этого алгоритма (например, [Анализ ключевых факторов влияния &#40;средств анализа таблиц для Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md)) непрерывные столбцы будут Binned мастером.  
  
-   При построении модели упрощенного алгоритма Байеса с помощью параметра [Расширенное моделирование &#40;надстройки интеллектуального анализа данных для Excel&#41;](advanced-modeling-data-mining-add-ins-for-excel.md) число столбцов будет удалено из модели. Если вы хотите избежать этого, используйте средство [переразметка &#40;SQL Server надстроек интеллектуального анализа данных&#41;](relabel-sql-server-data-mining-add-ins.md) средства, чтобы создать новый столбец со значениями binned.  
  
 **Модели кластеризации**  
  
-   Средства кластеризации ([Мастер кластеров &#40;надстройки интеллектуального анализа данных для excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) и [Определение категорий &#40;средства анализа таблиц для Excel&#41;](detect-categories-table-analysis-tools-for-excel.md)) также не могут использовать непрерывные числа, но оба эти средства автоматически забудут иметь номера столбцов.  
  
-   Оба инструмента дают возможность выбрать число выходных категорий в результатах, однако для управления группировкой значений в отдельных столбцах необходимо создать новый столбец с нужным группированием.  
  
 **Модели прогнозирования**  
  
-   Все средства прогнозирования предполагают, что прогнозируется непрерывное число. Нельзя прогнозировать число, сохраненное в виде текста.  
  
-   Если данные содержат числовые столбцы с неправильным типом данных, можно использовать функции Excel или PowerPivot, чтобы создать копию столбца с правильным числовым типом данных. При этом следует удалить копию столбца, который содержит текстовые числа, чтобы значения не дублировались.  
  
-   Если нужно создать точечную диаграмму модели регрессии, то входные переменные также должны быть непрерывными числами, выраженными соответствующим типом данных.  
  
### <a name="using-content-types-to-make-better-models"></a>Использование типов содержимого для получения оптимальных моделей  
 *Тип содержимого* — это свойство, которое применяется к столбцу для указания способа использования данных в модели. Алгоритм может использовать тип содержимого в виде инструкции или указания при анализе.  
  
 Например, если столбец содержит числа, повторяющиеся с некоторой периодичностью в соответствии с днями недели, можно указать тип содержимого как `Cyclical`.  
  
 При использовании мастеров и средств, предоставляемых в этой надстройке, не нужно беспокоиться о типах содержимого. Однако при использовании функции [Добавить модель к структуре &#40;надстройки интеллектуального анализа данных для Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md) моделирования для добавления новой модели к существующим данным может возникнуть ошибка, связанная с типами содержимого.  
  
 Это происходит потому, что некоторым типам моделей требуется определенный тип данных (например, метка времени). Средства обрабатывают эти столбцы в соответствии с конкретными требованиями и добавляют свойство типа содержимого. Поэтому при повторном использовании данных с совершенно другим алгоритмом может потребоваться изменение типа данных или типа содержимого.  
  
 Следующий список содержит типы содержимого, используемого в интеллектуальном анализе данных, и типы данных, которые их поддерживают.  
  
 `Discrete`  
 Столбец содержит конечное количество значений, между которыми нет континуума. Например, столбец с обозначением пола представляет собой типичный столбец для дискретного атрибута, в котором данные представляют конкретное количество категорий.  
  
 Тип содержимого `Discrete` может использоваться со всеми типами данных.  
  
 `Continuous`  
 Этот столбец содержит значения, которые представляют числовые данные в масштабе, допускающем применение промежуточных значений. Непрерывный столбец представляет данные измерений, при этом данные могут содержать бесконечное количество дробных значений. Примером столбца непрерывного атрибута может служить столбец с данными о температуре.  
  
 Тип содержимого `Continuous` может использоваться со следующими типами данных: `Date`, `Double` и `Long`.  
  
 `Discretized`  
 Столбец содержит значения, представляющие группы значений, полученных из непрерывного столбца. Контейнеры обрабатываются как **упорядоченные** и дискретные значения.  
  
 Тип содержимого `Discretized` может использоваться со следующими типами данных: `Date`, `Double`, `Long`.  
  
 **Клавиша**  
 Столбец, уникально определяющий строку.  
  
 Как правило, ключевой столбец — это числовой или текстовый идентификатор, который не может использоваться для анализа, а только для отслеживания записей. Исключения — это ключи временных рядов и ключи последовательности.  
  
 **Ключи вложенных таблиц** используются только при получении данных из внешнего источника данных, который был определен как представление источника данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] . Дополнительные сведения о вложенных таблицах см [https://msdn.microsoft.com/library/ms175659.aspx](https://msdn.microsoft.com/library/ms175659.aspx) . в следующих статьях:  
  
 Этот тип содержимого может использоваться со следующими типами данных: `Date`, `Double`, `Long` и `Text`.  
  
 **Ключевая последовательность**  
 Значения для этого столбца представляют собой последовательность событий. Значения упорядочены, но не должны обязательно находиться на одинаковом расстоянии друг от друга.  
  
 Этот тип содержимого поддерживается следующими типами данных: `Double`, `Long`, `Text` и `Date`.  
  
 **Ключевой столбец времени**  
 Столбец содержит упорядоченные значения, которые представляют шкалу времени. Тип содержимого Key Time можно использовать, только если модель является моделью временных рядов или моделью кластеризации последовательностей.  
  
 Данный тип содержимого поддерживается следующими типами данных: `Double`, `Long` и `Date`.  
  
 **Таблица**  
 Этот тип содержимого также используется только при получении данных из внешнего источника, который был определен как представление источника данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
 Это означает, что каждая строка данных фактически содержит вложенную таблицу с одним или несколькими столбцами и одной или несколькими строками.  
  
 Вложенные таблицы очень полезны, но их можно использовать только с [расширенным моделированием &#40;надстройки интеллектуального анализа данных для Excel&#41;](advanced-modeling-data-mining-add-ins-for-excel.md) параметры моделирования. Например, образец данных для [мастера взаимосвязей &#40;мастер&#41;клиента интеллектуального анализа данных для Excel](associate-wizard-data-mining-client-for-excel.md) и [анализ покупательской корзины &#40;таблица аналисистулс для Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) содержит данные, сведенные из вложенной таблицы.  

  
  
