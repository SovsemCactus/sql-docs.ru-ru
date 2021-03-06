---
title: Descending (расширения интеллектуального анализа данных) | Документация Майкрософт
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 2ef32a9e133c199aae0779c819736d77e0d15c45
ms.sourcegitcommit: 4cb53a8072dbd94a83ed8c7409de2fb5e2a1a0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83670058"
---
# <a name="isdescendant-dmx"></a>IsDescendant (расширения интеллектуального анализа данных)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Указывает, является ли текущий узел потомком заданного узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
IsDescendant(<NodeID>)  
```  
  
## <a name="return-type"></a>Тип возвращаемых данных  
 Тип Boolean.  
  
## <a name="remarks"></a>Комментарии  
 **Descending** используется только в [&#62; модели SELECT &#60;. CONTENT &#40;&#41;расширений интеллектуального анализа данных](../dmx/select-from-model-content-dmx.md) и [выберите из &#60;&#62; модели. DIMENSION_CONTENT &#40;запросы DMX&#41;](../dmx/select-from-model-dimension-content-dmx.md) .  
  
## <a name="examples"></a>Примеры  
 В приведенном ниже примере выдаются все объекты, которые являются потомками узла, заданного в функции IsDescendant.  
  
```  
SELECT * FROM [TM Decision Tree].CONTENT  
WHERE IsDescendant('00000000100')  
```  
  
## <a name="see-also"></a>См. также:  
 [Расширения интеллектуального анализа данных &#40;Справочник по функциям DMX&#41;](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Функции &#40;&#41;расширений интеллектуального анализа данных](../dmx/functions-dmx.md)   
 [Общие прогнозирующие функции &#40;&#41;расширений интеллектуального анализа данных](../dmx/general-prediction-functions-dmx.md)  
  
  
