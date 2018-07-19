---
title: Указание столбца, который используется как Регрессор в модели | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d8e0cb8e-302a-4166-9ed0-e2d9e2919b0a
caps.latest.revision: 6
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: a8d3418ced07536e0ab02c6ad1324096f0898bc6
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37293624"
---
# <a name="specify-a-column-to-use-as-regressor-in-a-model"></a>Указание столбца, который будет использоваться в модели в качестве регрессора
  Модель линейной регрессии представляет значение прогнозируемого атрибута как результат формулы, в которой входные данные комбинируются таким образом, чтобы они как можно ближе соответствовали предполагаемой линии регрессии. Этот алгоритм принимает только числовые значения и автоматически обнаруживает входные данные, которые обеспечивают наиболее близкое соответствие.  
  
 Однако можно указать, что столбец включается в качестве регрессора добавлением в модель параметра FORCE_REGRESSOR и указанием использования регрессоров. Это может понадобиться, когда атрибут имеет значение даже в том случае, если эффект слишком мал и не может быть обнаружен моделью либо когда необходимо обеспечить включение атрибута в формулу.  
  
 В следующей процедуре показано, как создать простую модель линейной регрессии с помощью образцов данных, использованных в [учебнике по нейронным сетям](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md). Модель не обязательно будет надежной, однако она демонстрирует, как использовать конструктор интеллектуального анализа данных для настройки модели линейной регрессии.  
  
### <a name="how-to-create-a-simple-linear-regression-model"></a>Как создать простую модель линейной регрессии  
  
1.  В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], в **обозревателе решений**разверните узел **Структуры интеллектуального анализа данных**.  
  
2.  Дважды щелкните Call Center.dmm, чтобы открыть его в конструкторе.  
  
3.  В меню **Модель интеллектуального анализа данных** выберите пункт **Создать модель интеллектуального анализа данных**.  
  
4.  В качестве алгоритма выберите **Алгоритм линейной регрессии (Майкрософт)**. В качестве имени введите **Call Center Regression**.  
  
5.  На вкладке **Модели интеллектуального анализа данных** измените использование столбца следующим образом. Все столбцы, отсутствующие в следующем списке, должны быть установлены в значение **Пропустить**.  
  
     FactCallCenterID**Key**  
  
     ServiceGrade**PredictOnly**  
  
     Total Operators**Input**  
  
     AverageTimePerIssue**Input**  
  
6.  В меню **Модель интеллектуального анализа данных** выберите команду **Задать параметры модели**.  
  
7.  Для параметра FORCE_REGRESSOR в столбце **Значение** перечислите через запятую имена столбцов, заключенные в квадратные скобки, следующим образом:  
  
    ```  
    [Average Time Per Issue],[Total Operators]  
    ```  
  
    > [!NOTE]  
    >  Алгоритм автоматически обнаруживает столбцы, являющиеся лучшими регрессорами. Нужно только при необходимости принудительно использовать регрессоры, чтобы обеспечить включение столбца в конечную формулу.  
  
8.  В меню **Модель интеллектуального анализа данных** выберите пункт **Обработать модель**.  
  
     В средстве просмотра модель представляется единственным узлом, содержащим формулу регрессии. Можно просмотреть формулу в окне **Обозначения интеллектуального анализа данных**или получить коэффициенты для формулы с помощью запросов.  
  
## <a name="see-also"></a>См. также  
 [Алгоритм линейной регрессии (Майкрософт)](microsoft-linear-regression-algorithm.md)   
 [Запросы интеллектуального анализа данных](data-mining-queries.md)   
 [Технический справочник по алгоритму линейной регрессии Майкрософт](microsoft-linear-regression-algorithm-technical-reference.md)   
 [Модель интеллектуального анализа данных для моделей линейной регрессии &#40;службы Analysis Services — Интеллектуальный анализ данных&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  