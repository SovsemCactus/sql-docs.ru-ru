---
title: Указание типа данных и типа содержимого (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 72484d27-3ef1-4f16-813c-2f43231fc2da
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 583a6fda2dbb4698405a3d69f33955531b3c1c10
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2020
ms.locfileid: "62720053"
---
# <a name="specifying-the-data-type-and-content-type-basic-data-mining-tutorial"></a>Указание типа данных и типа содержимого (учебник по интеллектуальному анализу данных — начальный уровень)
  Теперь, после выбора столбцов для построения структуры и обучения моделей, необходимо внести изменения в данные по умолчанию и в типы содержимого, заданные мастером.  
  
#### <a name="review-and-modify-content-type-and-data-type-for-each-column"></a>Просмотр и изменение типа содержимого и типа данных для каждого столбца  
  
1.  На странице **Определение содержимого и типа данных столбцов** нажмите кнопку **обнаружить** , чтобы запустить алгоритм, который определяет данные по умолчанию и типы содержимого для каждого столбца.  
  
2.  Проверьте записи в столбцах **тип содержимого** и **тип данных** и при необходимости измените их, чтобы убедиться, что параметры совпадают с параметрами, перечисленными в следующей таблице.  
  
     Обычно мастер распознает числа и присваивает им соответствующий числовой тип данных, но часто бывает нужно обрабатывать числа как строки. Например, **GeographyKey** должен обрабатываться как текст, так как в этом случае было бы неуместно выполнять математические операции с этим идентификатором.  
  
    |Столбец|Тип содержимого|Тип данных|  
    |------------|------------------|---------------|  
    |**Адрес строка1**|**Discrete**|**Текст**|  
    |**Адрес строка2**|**Discrete**|**Текст**|  
    |**Интервал**|**Обеспечения**|**Поддерживаем**|  
    |**Покупатель велосипеда**|**Discrete**|**Поддерживаем**|  
    |**Расстояние до работы**|**Discrete**|**Текст**|  
    |**CustomerKey**|**Клавиша**|**Поддерживаем**|  
    |**DateLastPurchase**|**Обеспечения**|**Дата**|  
    |**Адрес электронной почты**|**Discrete**|**Текст**|  
    |**English Education**|**Discrete**|**Текст**|  
    |**English Occupation**|**Discrete**|**Текст**|  
    |**Фамилия**|**Discrete**|**Текст**|  
    |**Gender**|**Discrete**|**Текст**|  
    |**Geography Key**|**Discrete**|**Текст**|  
    |**House Owner Flag**|**Discrete**|**Текст**|  
    |**Фамилия**|**Discrete**|**Текст**|  
    |**Семейное положение**|**Discrete**|**Текст**|  
    |**Number Cars Owned**|**Discrete**|**Поддерживаем**|  
    |**Число детей в домашней сети**|**Discrete**|**Поддерживаем**|  
    |**Регион**|**Discrete**|**Текст**|  
    |**Общее количество детей**|**Discrete**|**Поддерживаем**|  
    |**Годовой доход**|**Обеспечения**|**Double**|  
  
3.  Нажмите кнопку **Далее**.  
  
## <a name="next-task-in-lesson"></a>Следующая задача занятия  
 [Указание набора проверочных данных для &#40;учебника по интеллектуальному анализу данных Basic&#41;](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a>Предыдущая задача занятия  
 [Создание структуры модели интеллектуального анализа данных с целевой корреспонденцией &#40;учебник по основам интеллектуального анализа&#41;](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>См. также  
 [Типы содержимого &#40;&#41;интеллектуального анализа данных](../../2014/analysis-services/data-mining/content-types-data-mining.md)   
 [Типы данных (интеллектуальный анализ данных)](../../2014/analysis-services/data-mining/data-types-data-mining.md)  
  
  
