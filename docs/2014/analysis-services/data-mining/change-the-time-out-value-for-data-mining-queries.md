---
title: Изменение значения времени ожидания для запросов интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time-out
ms.assetid: f1add4bc-e882-440a-a98b-333cfa274c3e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dcdcdcbb6e2aef48dd8725f10f38180c73f5f6c
ms.sourcegitcommit: 2f166e139f637d6edfb5731510d632a13205eb25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84524918"
---
# <a name="change-the-time-out-value-for-data-mining-queries"></a>изменить значение времени ожидания для запросов интеллектуального анализа данных
  При построении диаграммы точности прогнозов или выполнении прогнозирующего запроса иногда может потребоваться много времени для создания всех данных, необходимых для формирования прогноза. Чтобы предотвратить возможность завершения запроса из-за истечения времени ожидания, можно изменить значение, управляющее тем, как долго сервер служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ожидает завершения запроса.  
  
 Значение по умолчанию равно 15, но этого может оказаться недостаточно, если модели являются сложными или источник данных имеет большой размер. При необходимости можно намного увеличить это значение, чтобы отвести достаточное количество времени для обработки. Например, если значение **Время ожидания запроса** равно 600, выполнение запроса может продолжаться до 10 минут.  
  
 Дополнительные сведения о прогнозирующих запросах см. в разделе [Задачи и инструкции по запросам интеллектуального анализа данных](data-mining-query-tasks-and-how-tos.md).  
  
### <a name="configure-the-time-out-value-for-data-mining-queries"></a>Настройка значения времени ожидания для запросов интеллектуального анализа данных  
  
1.  В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]в меню **Сервис** выберите пункт **Параметры**.  
  
2.  На панели **Параметры** разверните элемент **Конструкторы бизнес-аналитики**.  
  
3.  В текстовое поле **Время ожидания запроса** введите значение в секундах.  
  
## <a name="see-also"></a>См. также:  
 [Задачи и инструкции по запросам интеллектуального анализа данных](data-mining-query-tasks-and-how-tos.md)   
 [Запросы интеллектуального анализа данных](data-mining-queries.md)  
  
  
