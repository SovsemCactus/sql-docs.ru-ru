---
title: Прогноз взаимосвязей (учебник по интеллектуальному анализу интеллектуальному анализу данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 9140c5f2-b340-45a6-9c27-d870d15aafea
caps.latest.revision: 21
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 79555990296cc3ecd0b30bb2cd3de92b6adabb50
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37187711"
---
# <a name="predicting-associations-intermediate-data-mining-tutorial"></a>Прогноз взаимосвязей (учебник по интеллектуальному анализу данных — средний уровень)
  После обработки моделей для создания прогнозов можно использовать сведения о взаимосвязях, хранящиеся в модели. В последней задаче этого занятия предстоит изучить, как создавать прогнозирующие запросы к созданным моделям взаимосвязей. В этом занятии предполагается, что вы знакомы с работой построителя прогнозирующих запросов и хотите научиться создавать прогнозирующие запросы к моделям взаимосвязей. Дополнительные сведения том, как использовать построитель прогнозирующих запросов, см. в разделе [интерфейсы запросов данных для интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-query-tools.md).  
  
## <a name="creating-a-singleton-prediction-query"></a>Создание одноэлементных прогнозирующих запросов  
 Прогнозирующие запросы для модели взаимосвязей могут быть весьма полезными:  
  
-   Рекомендуйте клиентам элементы на основе предыдущих или связанных покупок  
  
-   Найдите связанные события.  
  
-   Определите отношения в наборах транзакций или через них.  
  
 Чтобы создать прогнозирующий запрос, сначала необходимо выбрать модель взаимосвязей, которая будет использоваться, а затем указать входные данные. Входные данные могут поступать из внешнего источника данных, например из списка значений, или можно создать одноэлементный запрос и предоставить значения по ходу выполнения операции.  
  
 В этом сценарии сначала будет создано несколько одноэлементных прогнозирующих запросов, чтобы получить представление о том, как работает прогнозирование. Затем будет создан запрос для пакетных прогнозов, которые можно использовать для предоставления рекомендаций на основании текущих покупок клиента.  
  
#### <a name="to-create-a-prediction-query-on-an-association-model"></a>Создание прогнозирующего запроса для модели взаимосвязей  
  
1.  Нажмите кнопку **модель интеллектуального анализа данных** конструкторе интеллектуального анализа данных.  
  
2.  В **модель интеллектуального анализа данных** панели щелкните **Выбор модели**. (Если нужная модель уже выбрана, этот и следующий шаги можно пропустить.)  
  
3.  В **Выбор модели интеллектуального анализа данных** диалоговом окне разверните узел, представляющий структуру интеллектуального анализа данных **ассоциации**и выберите модель **ассоциации**. Нажмите кнопку **ОК**.  
  
     На данном этапе можно не учитывать входную панель.  
  
4.  В сетке щелкните пустую ячейку под **источника** и выберите **Прогнозирующая функция.** В ячейке под **поле**выберите `PredictAssociation`.  
  
     Можно также использовать **Predict** функцию для прогноза взаимосвязей. Если вы обязательно выберите версию **Predict** функцию, которая принимает в качестве аргумента столбец таблицы.  
  
5.  В **модель интеллектуального анализа данных** области, выберите вложенную таблицу `vAssocSeqLineItems`и перетащите его в сетке до **критерий или аргумент** поле для `PredictAssociation` функции.  
  
     Путем перетаскивания имен таблиц и столбцов можно создавать сложные инструкции без синтаксических ошибок. Тем не менее, он заменяет текущее содержимое ячейки, которая включает другие необязательные аргументы для `PredictAssociation` функции. Чтобы просмотреть другие аргументы, можно на время добавить в сетку второй экземпляр функции и использовать его для справки.  
  
6.  Нажмите кнопку **критерий или аргумент** поле и введите следующий текст после имени таблицы: `,3`  
  
     Полный текст **критерий или аргумент** окно должно выглядеть следующим образом:  
  
     `[Association].[v Assoc Seq Line Items],3`  
  
7.  Нажмите кнопку **результаты** кнопку в верхнем углу построителя прогнозирующих запросов.  
  
 Ожидаемые результаты содержат один столбец с заголовком **выражение**. **Выражение** столбец содержит вложенную таблицу с одним столбцом и следующими тремя строками. Поскольку входное значение не было указано, эти прогнозы представляют наиболее вероятные взаимосвязи продуктов для модели в целом.  
  
|Модель|  
|-----------|  
|Женские шорты Mountain|  
|Фляга для воды|  
|Touring-3000|  
  
 Далее будет использоваться **одноэлементного запроса** панели, чтобы указать продукт в качестве входных данных для запроса и просмотреть продукты, которые, скорее связаны с этим элементом.  
  
#### <a name="to-create-a-singleton-prediction-query-with-nested-table-inputs"></a>Создание одноэлементного прогнозирующего запроса с входными данными вложенной таблицы  
  
1.  Нажмите кнопку **разработки** кнопку в углу построителя прогнозирующих запросов, чтобы вернуться в сетку построения запросов.  
  
2.  На **модель интеллектуального анализа данных** меню, выберите **одноэлементный запрос**.  
  
3.  В **модель интеллектуального анализа данных** выберите **ассоциации** модели.  
  
4.  В сетке щелкните пустую ячейку под **источника** и выберите **Прогнозирующая функция.** В ячейке под **поле**выберите `PredictAssociation`.  
  
5.  В **модель интеллектуального анализа данных** области, выберите вложенную таблицу `vAssocSeqLineItems`и перетащите его в сетке до **критерий или аргумент** поле для `PredictAssociation` функции. Тип `,3` после имени вложенной таблицы, как в предыдущей процедуре.  
  
6.  В **одноэлементного запроса** диалоговом окне щелкните **значение** рядом **vAssoc Seq Line Items**, а затем нажмите кнопку **(...)**  кнопки.  
  
7.  В **Вход вложенной таблицы** выберите `Touring Tire` в **ключевой столбец** области, а затем щелкните **добавить**.  
  
8.  Нажмите кнопку **результаты** кнопки.  
  
 Теперь в результатах отображаются прогнозы для продуктов, которые с наибольшей вероятностью связаны с шинами для туристических велосипедов.  
  
|Модель|  
|-----------|  
|Камера для покрышки туристического велосипеда|  
|Sport-100|  
|Фляга для воды|  
  
 В результате изучения модели уже становится известно, что камера шины для велосипеда часто приобретается вместе с шиной. Теперь вас больше интересует то, какие продукты можно порекомендовать клиентам, купившим оба этих элемента. Запрос необходимо изменить таким образом, чтобы спрогнозировать связанные продукты на основании двух элементов в корзине. Также в запрос нужно добавить степень вероятности для каждого прогнозируемого продукта.  
  
#### <a name="to-add-inputs-and-probabilities-to-the-singleton-prediction-query"></a>Добавление входных данных и вероятностей в одноэлементный прогнозирующий запрос  
  
1.  Нажмите кнопку **разработки** кнопку в углу построителя прогнозирующих запросов, чтобы вернуться в сетку построения запросов.  
  
2.  В **одноэлементного запроса** диалоговом окне щелкните **значение** рядом **vAssoc Seq Line Items**, а затем нажмите кнопку **(...)**  кнопки.  
  
3.  В **ключевой столбец** области выберите `Touring Tire`, а затем нажмите кнопку **добавить**.  
  
4.  В сетке щелкните пустую ячейку под **источника** и выберите **Прогнозирующая функция.** В ячейке под **поле**выберите `PredictAssociation`.  
  
5.  В **модель интеллектуального анализа данных** области, выберите вложенную таблицу `vAssocSeqLineItems`и перетащите его в сетке до **критерий или аргумент** поле для `PredictAssociation` функции. Тип `,3` после имени вложенной таблицы, как в предыдущей процедуре.  
  
6.  В **Вход вложенной таблицы** выберите `Touring Tire Tube` в **ключевой столбец** области, а затем щелкните **добавить**.  
  
7.  В сетке щелкните строку для `PredictAssociation` функцию, нажмите кнопку **критерий или аргумент** поле и измените аргументы таким образом, чтобы добавить аргумент INCLUDE_STATISTICS.  
  
     Полный текст **критерий или аргумент** окно должно выглядеть следующим образом:  
  
     `[Association].[v Assoc Seq Line Items], INCLUDE_STATISTICS, 3`  
  
8.  Нажмите кнопку **результаты** кнопки.  
  
 Результаты во вложенной таблице меняются, отображая прогнозы вместе с поддержкой и вероятностью. Дополнительные сведения о том, как интерпретировать эти значения, см. в разделе [интеллектуального анализа данных модели содержимого для моделей взаимосвязей &#40;службы Analysis Services — Интеллектуальный анализ данных&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-association-models-analysis-services-data-mining.md).  
  
|Модель|$SUPPORT|$PROBABILITY|$ADJUSTEDPROBABILITY|  
|-----------|--------------|------------------|--------------------------|  
|Sport-100|4334|0.291...|0.252...|  
|Фляга для воды|2866|0.192...|0.175...|  
|Ремонтный комплект|2113|0,142...|0.132|  
  
## <a name="working-with-results"></a>Работа с результатами  
 Если результаты содержат много вложенных таблиц, такие результаты можно преобразовать в плоский формат для более удобного просмотра. С этой целью можно вручную изменить запрос и добавить ключевое слово `FLATTENED`.  
  
#### <a name="to-flatten-nested-rowsets-in-a-prediction-query"></a>Преобразование вложенных наборов строк в плоский формат в прогнозирующем запросе  
  
1.  Нажмите кнопку **SQL** кнопку в углу построителя прогнозирующих запросов.  
  
     Сетка будет преобразована в открытую панель, в которой можно просмотреть и изменить инструкцию DMX, созданную построителем прогнозирующих запросов.  
  
2.  После ключевого слова `SELECT` введите `FLATTENED`.  
  
     Полный текст запроса должен иметь следующий вид:  
  
    ```  
    SELECT FLATTENED  
      PredictAssociation([Association].[v Assoc Seq Line Items],INCLUDE_STATISTICS,3)  
    FROM  
      [Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Touring Tire' AS [Model]  
      UNION SELECT 'Touring Tire Tube' AS [Model]) AS [v Assoc Seq Line Items]) AS t  
    ```  
  
3.  Нажмите кнопку **результаты** кнопку в верхнем углу построителя прогнозирующих запросов.  
  
 Следует отметить, что после редактирования запроса вручную нельзя вернуться в конструктор, не потеряв изменения. Чтобы сохранить запрос, созданную инструкцию DMX можно вручную скопировать в текстовый файл. При возврате в конструктор в нем восстанавливается последняя версия запроса, имевшаяся до выхода из него.  
  
## <a name="creating-multiple-predictions"></a>Создание нескольких прогнозов  
 Предположим, необходимо получить наилучшие прогнозы для отдельных клиентов на основании их прошлых покупок. Можно использовать внешние данные в качестве входных данных для прогнозирующего запроса, например таблицы, содержащие идентификаторы клиентов и их последние покупки товаров. При этом требуется, чтобы таблицы данных уже были определены как представление источника данных служб Analysis Services. Кроме того, входные данные должны содержать таблицы вариантов и вложенные таблицы наподобие тех, которые используются в модели. Им не обязательно иметь одинаковые имена, но структура должна быть сходной. В целях этого учебника будут использоваться исходные таблицы, которые применялись для обучения модели.  
  
#### <a name="to-change-the-input-method-for-the-prediction-query"></a>Изменение метода ввода для прогнозирующего запроса  
  
1.  В **модель интеллектуального анализа данных** меню, выберите **одноэлементный запрос** опять же, снимите флажок.  
  
2.  Появится сообщение об ошибке, предупреждая о том, что одноэлементный запрос будет утерян. Нажмите кнопку **Да**.  
  
     Имя диалогового окна ввода меняется на **Выбор входных таблиц**.  
  
 Поскольку необходимо создать прогнозирующий запрос, предоставляющий идентификатор клиента и список продуктов в качестве входных данных, потребуется добавить таблицу клиентов в качестве таблицы вариантов и таблицу покупок в качестве вложенной таблицы. Затем нужно добавить прогнозирующие функции для создания рекомендаций.  
  
#### <a name="to-create-a-prediction-query-using-nested-table-inputs"></a>Создание прогнозирующего запроса с использованием входных данных вложенной таблицы  
  
1.  На панели «Модель интеллектуального анализа данных» выберите «Фильтруемые взаимосвязи».  
  
2.  В **Выбор входных таблиц** диалоговом окне щелкните **выбрать таблицу вариантов**.  
  
3.  В **Выбор таблицы** диалоговом окне для **источника данных**, выберите AdventureWorksDW2008. В **имя таблицы или представления** выберите vAssocSeqOrders, а затем нажмите кнопку **ОК**.  
  
     Таблица vAssocSeqOrders добавляется на панель.  
  
4.  В **Выбор входных таблиц** диалоговом окне щелкните **выбрать вложенную таблицу**.  
  
5.  В **Выбор таблицы** диалоговом окне для **источника данных**, выберите AdventureWorksDW2008. В **имя таблицы или представления** выберите vAssocSeqLineItems, а затем нажмите кнопку **ОК**.  
  
     Таблица vAssocSeqLineItems добавляется на панель.  
  
6.  В **определение вложенного соединения** диалоговое окно, перетащите поле из таблицы вариантов OrderNumber и перетащите поле OrderNumber вложенной таблицы.  
  
     Можно также щелкнуть **Добавление отношения** и создать связь путем выбора из списка столбцов.  
  
7.  В **укажите отношение** диалогового окна убедитесь, что правильном сопоставлении полей OrderNumber и нажмите кнопку **ОК**.  
  
8.  Нажмите кнопку **ОК** закрыть **определение вложенного соединения** диалоговое окно.  
  
     Таблица вариантов и вложенная таблица обновляются на панели конструирования для отображения соединений между столбцами внешних данных и столбцами модели. Если связи неправильные, можно правой кнопкой мыши соединительную линию и выберите **изменить соединения** для редактирования столбца сопоставление, или можно правой кнопкой мыши соединительную линию и выберите **удалить** для удаления связь полностью.  
  
9. Добавьте в сетку новую строку. Для **источника**выберите **таблицы vAssocSeqOrders**. Для **поле**, выберите CustomerKey.  
  
10. Добавьте в сетку новую строку. Для **источника**выберите **таблицы vAssocSeqOrders**. Для **поле**, выберите регион.  
  
11. Добавьте в сетку новую строку. Для **источника**выберите **Прогнозирующая функция**и для **поле**выберите `PredictAssociation`.  
  
12. Перетащите vAssocSeqLineItems в **критерий или аргумент** поле `PredictAssociation` строки. Щелкните в конце **критерий или аргумент** поле и введите следующий текст: `INCLUDE_STATISTICS,3`  
  
     Полный текст **критерий или аргумент** поле должно быть: `[Association].[v Assoc Seq Line Items], INCLUDE_STATISTICS, 3`  
  
13. Нажмите кнопку **результат** кнопку, чтобы просмотреть прогнозы для каждого клиента.  
  
 Можно попытаться создать подобный прогнозирующий запрос для нескольких моделей и узнать, изменятся ли результаты прогнозов после фильтрации. Дополнительные сведения о создании прогнозов и других типов запросов, см. в разделе [примеры запросов моделей взаимосвязей](../../2014/analysis-services/data-mining/association-model-query-examples.md).  
  
## <a name="see-also"></a>См. также  
 [Модель интеллектуального анализа данных для моделей взаимосвязей &#40;службы Analysis Services — Интеллектуальный анализ данных&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-association-models-analysis-services-data-mining.md)   
 [PredictAssociation &#40;расширений интеллектуального анализа данных&#41;](/sql/dmx/predictassociation-dmx)   
 [Создание прогнозирующего запроса с помощью построителя прогнозирующих запросов](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  