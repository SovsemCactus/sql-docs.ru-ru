---
title: IsTrainingCase (расширения интеллектуального анализа данных) | Документация Майкрософт
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: a1c2719323bad884db77860590d0a95080c1a234
ms.sourcegitcommit: 4cb53a8072dbd94a83ed8c7409de2fb5e2a1a0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83670202"
---
# <a name="istrainingcase-dmx"></a>IsTrainingCase (расширения интеллектуального анализа данных)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Указывает, используется ли вариант в качестве обучающего для конкретной модели или структуры интеллектуального анализа данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
IsTrainingCase()  
```  
  
## <a name="result-type"></a>Тип результата  
 Возвращает **значение true** , если вариант является частью набора обучающих данных. в противном случае — **false**.  
  
## <a name="remarks"></a>Комментарии  
 Если создание структуры интеллектуального анализа данных и соответствующей модели интеллектуального анализа производится при помощи мастера интеллектуального анализа данных, то по умолчанию 30% вариантов резервируются для использования в качестве проверочного набора данных. Оставшиеся варианты в выбранном источнике данных будут использоваться для обучения модели. Однако если для создания модели интеллектуального анализа данных использовались расширения интеллектуального анализа данных, то по умолчанию все данные используются для обучения модели и проверочный набор не создается. Чтобы разрешить создание проверочного набора данных, нужно задать значение параметров предложения WITH HOLDOUT.  
  
 Узнать, были ли данные конкретной структуры интеллектуального анализа данных разделены на обучающие и проверочные, можно, посмотрев значение свойств <xref:Microsoft.AnalysisServices.MiningStructure.HoldoutMaxCases%2A> и <xref:Microsoft.AnalysisServices.MiningStructure.HoldoutMaxPercent%2A>.  
  
> [!NOTE]  
>  Детализация должна быть включена в модели, если вы хотите использовать функции IsTrainingCase или IsTestCase, чтобы получить сведения о вариантах в модели. Дополнительные сведения см. в разделе [Включение детализации для модели интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/enable-drillthrough-for-a-mining-model).  
  
 Чтобы вернуть варианты, которые являются частью набора проверочных данных, используйте функцию [IsTestCase &#40;DMX&#41;](../dmx/istestcase-dmx.md).  
  
## <a name="examples"></a>Примеры  
 В следующем примере модель интеллектуального анализа данных кластеризации используется из сценария целевой рассылки в [учебнике по базовому интеллектуальному анализу данных](https://msdn.microsoft.com/library/6602edb6-d160-43fb-83c8-9df5dddfeb9c). Этот запрос возвращает только варианты, которые использовались для обучения модели интеллектуального анализа данных. Помимо этого обучающие варианты будут ограничены условием, что покупатель моложе 40 лет.  
  
```  
SELECT *  
FROM [TM Clustering].CASES  
WHERE IsTrainingCase()  
AND [Age] <40  
```  
  
 Другие примеры запросов к вариантам, используемым в интеллектуальном анализе данных, см. в разделе [Выбор из &#60;модели&#62;. В случаях &#40;&#41;расширений интеллектуального анализа данных](../dmx/select-from-model-cases-dmx.md) и [выберите &#60;структура&#62;. ВАРИАНТОВ](../dmx/select-from-structure-cases.md).  
  
## <a name="see-also"></a>См. также:  
 [Обучающие и проверочные наборы данных](https://docs.microsoft.com/analysis-services/data-mining/training-and-testing-data-sets)   
 [Функции &#40;&#41;расширений интеллектуального анализа данных](../dmx/functions-dmx.md)   
 [Запросы интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/data-mining-queries)  
  
  
