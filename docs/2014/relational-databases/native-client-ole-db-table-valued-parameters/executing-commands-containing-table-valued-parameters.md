---
title: Выполнение команд, содержащих возвращающие табличные значения параметры | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, executing commands containing
ms.assetid: 7ecba6f6-fe7a-462a-9aa3-d5115b6d4529
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f22a024b0edddbcc6cad17cecb62aa026b8a6b1
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85038926"
---
# <a name="executing-commands-containing-table-valued-parameters"></a>Выполняет команды, содержащие возвращающие табличное значение параметры
  Выполнение команд, содержащих возвращающие табличное значение параметры, проводится в две стадии.  
  
1.  Задать тип параметра.  
  
2.  Выполнить привязку данных параметра.  
  
## <a name="table-valued-parameter-specification"></a>Спецификация возвращающих табличные значения параметров  
 Потребитель может указать тип возвращающего табличные значения параметра. В эту информацию входит имя возвращающего табличное значение параметра. Кроме того, в нее входит имя схемы, если тип определенной пользователем таблицы для возвращающего табличное значение параметра не входит в текущую используемую по умолчанию схему соединения. В зависимости от поддержки на сервере потребитель может также указать необязательную информацию о метаданных (например, упорядочение столбцов), и указать, что все строки конкретных столбцов имеют значения по умолчанию.  
  
 Чтобы указать возвращающий табличное значение параметр, потребитель вызывает ISSCommandWithParameter::SetParameterInfo и при необходимости — ISSCommandWithParameters:: SetParameterProperties. Для возвращающего табличное значение параметра поле *pwszDataSourceType* структуры DBPARAMBINDINFO имеет значение DBTYPE_TABLE. Полю *ulParamSize* присваивается значение ~0, которое указывает, что длина неизвестна. Конкретные свойства возвращающих табличное значение параметров, таких как имя схемы, имя типа, порядок столбцов, столбцы по умолчанию, можно задать с помощью метода ISSCommandWithParameters::SetParameterProperties.  
  
## <a name="table-valued-parameter-binding"></a>Привязка возвращающих табличные значения параметров  
 Возвращающий табличное значение параметр может представлять собой любой объект — набор рядов. Поставщик читает этот объект при отправке возвращающих табличное значение параметров на сервер во время выполнения.  
  
 Чтобы привязать возвращающий табличное значение параметр, потребитель вызывает метод IAccessor::CreateAccessor. Полю *wType* структуры DBBINDING возвращающего табличное значение параметра присваивается значение DBTYPE_TABLE. Элемент *pObject* структуры DBBINDING имеет значение, отличное от NULL, а элементу *iid* элемента *pObject* присваивается значение IID_IRowset или интерфейсы любых других объектов — наборов строк возвращающего табличное значение параметра. Остальным полям структуры DBBINDING значения присваиваются так же, как для объектов BLOB с потоковым обновлением.  
  
 При привязке возвращающего табличное значение параметра и связанного с ним объекта набора строк действуют следующие ограничения.  
  
-   Для данных столбцов набора строк возвращающего табличное значение параметра допускаются только состояния DBSTATUS_S_ISNULL и DBSTATUS_S_OK. Передача значения DBSTATUS_S_DEFAULT приведет к ошибке, и состоянию привязки будет присвоено значение DBSTATUS_E_BADSTATUS.  
  
-   Возвращающий табличное значение параметр может иметь значение состояния DBSTATUS_S_DEFAULT. Допускаются только значения DBSTATUS_S_DEFAULT и DBSTATUS_S_OK. Если состояние равно DBSTATUS_S_DEFAULT, возвращающий табличное значение параметр соответствует пустой таблице.  
  
-   Столбцы «только для чтения» возвращающего табличное значение параметра (столбцы-идентификаторы и вычисляемые столбцы) должны быть помечены как значения по умолчанию с помощью свойства SSPROP_PARAM_TABLE_DEFAULT_COLUMNS. Столбцы, имеющие значения по умолчанию, следует также пометить как значения по умолчанию с помощью свойства SSPROP_PARAM_TABLE_DEFAULT_COLUMNS, чтобы их можно было использовать как значения данных столбца для конкретного возвращающего табличное значение параметра. Поставщик не учитывает значения данных, привязанные к столбцам, помеченным как столбцы по умолчанию.  
  
-   Данные для столбцов с атрибутом DPPROP_COL_AUTOINCREMENT или SSPROP_COL_COMPUTED будут переданы на сервер, за исключением столбцов, для которых также задан атрибут SSPROP_PARAM_TABLE_DEFAULT.  
  
## <a name="see-also"></a>См. также:  
 [Возвращающие табличное значение параметры &#40;OLE DB&#41;](table-valued-parameters-ole-db.md)   
 [Использование возвращающих табличные значения параметров &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
