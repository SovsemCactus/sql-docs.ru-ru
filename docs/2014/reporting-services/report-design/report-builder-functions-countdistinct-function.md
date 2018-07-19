---
title: Функция CountDistinct (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 902c251e-e1e8-41d2-ac20-5bb6138ac410
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 37fc5f2045f2fcf232ab8984ff83aa2ed3abb230
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37227024"
---
# <a name="countdistinct-function-report-builder-and-ssrs"></a>Функция CountDistinct (построитель отчетов и службы SSRS)
  Возвращает количество уникальных значений, отличных от NULL, определяемое выражением, вычисляемым в контексте данной области.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
CountDistinct(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a>Параметры  
 *expression*  
 (`Variant`) Выражение, к которому статистическая обработка.  
  
 *область*  
 (`String`) Необязательно. Имя набора данных, группы или области данных, содержащих элементы отчета, к которым применяется агрегатная функция. Если аргумент *scope* не задан, используется текущая область.  
  
 *рекурсивные*  
 (**Перечислимый тип**) Необязательно. `Simple` (по умолчанию) или `RdlRecursive`. Указывает, нужно ли выполнять статистическую обработку рекурсивно.  
  
## <a name="return-type"></a>Тип возвращаемых данных  
 Возвращает `Integer`.  
  
## <a name="remarks"></a>Примечания  
 Значение *scope* должно быть строковой константой и не может быть выражением. Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область. Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.  
  
 *Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.  
  
-   Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее. Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.  
  
-   Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.  
  
-   *Выражение* не может содержать `First`, `Last`, `Previous`, или `RunningValue` функции.  
  
-   *Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.  
  
 Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).  
  
 Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере кода показано выражение, вычисляющее количество уникальных значений `Size` , отличных от NULL, для области по умолчанию и области родительской группы. Выражение добавляется в ячейку строки, относящуюся к дочерней группе `GroupbySubcategory`. Родительской группой является `GroupbyCategory`. Выражение отображает результаты для группы `GroupbySubcategory` (область по умолчанию) и затем для группы `GroupbyCategory` (область родительской группы).  
  
> [!NOTE]  
>  Выражения не должны содержать действительные возвраты каретки и разрывы строк; они включаются в пример кода для поддержки модулей подготовки отчетов. При копировании следующего примера удалите возвраты каретки изо всех строк.  
  
```  
="Distinct count (Subcategory): " & CountDistinct(Fields!Size.Value) &   
"Distinct count (Category): " & CountDistinct(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a>См. также  
 [Использование выражений в отчетах &#40;построитель отчетов и службы SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md)   
 [Типы данных в выражениях (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md)   
 [Область выражения для суммирования, агрегатов и встроенных коллекций &#40;построитель отчетов и службы SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  