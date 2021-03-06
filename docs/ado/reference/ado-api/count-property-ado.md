---
title: Свойство Count (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Collection::Count
helpviewer_keywords:
- Count property [ADO]
ms.assetid: da9ccd1f-d402-41a2-940c-45556fc5340d
author: rothja
ms.author: jroth
ms.openlocfilehash: 9b611546b63dec8484785ba855f299925933e89e
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760240"
---
# <a name="count-property-ado"></a>Свойство Count (ADO)
Указывает количество объектов в коллекции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение **типа Long** .  
  
## <a name="remarks"></a>Примечания  
 Для определения количества объектов в заданной коллекции используется свойство **Count** .  
  
 Поскольку нумерация элементов коллекции начинается с нуля, всегда следует создавать циклы кода, начиная с нуля и заканчивая значением свойства **Count** минус 1. Если вы используете Microsoft Visual Basic и хотите перебрать элементы коллекции, не проверяя свойство **Count** , используйте оператор **For Each... Следующая** команда.  
  
 Если свойство **Count** равно нулю, в коллекции отсутствуют объекты.  
  
## <a name="applies-to"></a>Применяется к  
  
||||  
|-|-|-|  
|[Коллекция Axes (многомерные объекты ADO)](../../../ado/reference/ado-md-api/axes-collection-ado-md.md)|[Коллекция Columns (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)|[Коллекция CubeDefs (многомерные объекты ADO)](../../../ado/reference/ado-md-api/cubedefs-collection-ado-md.md)|  
|[Коллекция Dimensions (многомерные объекты ADO)](../../../ado/reference/ado-md-api/dimensions-collection-ado-md.md)|[Коллекция Errors (ADO)](../../../ado/reference/ado-api/errors-collection-ado.md)|[Коллекция Fields (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)|  
|[Коллекция Groups (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)|[Коллекция Hierarchies (многомерные объекты ADO)](../../../ado/reference/ado-md-api/hierarchies-collection-ado-md.md)|[Коллекция Indexes (ADOX)](../../../ado/reference/adox-api/indexes-collection-adox.md)|  
|[Коллекция Keys (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)|[Коллекция Levels (многомерные объекты ADO)](../../../ado/reference/ado-md-api/levels-collection-ado-md.md)|[Коллекция Members (многомерные объекты ADO)](../../../ado/reference/ado-md-api/members-collection-ado-md.md)|  
|[Коллекция Parameters (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)|[Коллекция Positions (многомерные объекты ADO)](../../../ado/reference/ado-md-api/positions-collection-ado-md.md)|[Коллекция Procedures (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)|  
|[Коллекция Properties (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)|[Коллекция Tables (ADOX)](../../../ado/reference/adox-api/tables-collection-adox.md)|[Коллекция Users (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)|  
|[Коллекция Views (ADOX)](../../../ado/reference/adox-api/views-collection-adox.md)|||  
  
## <a name="see-also"></a>См. также  
 [Пример свойства Count (Visual Basic)](../../../ado/reference/ado-api/count-property-example-vb.md)   
 [Пример свойства Count (Visual c++)](../../../ado/reference/ado-api/count-property-example-vc.md)   
 [Метод Refresh (ADO)](../../../ado/reference/ado-api/refresh-method-ado.md)
