---
title: Пакетный режим | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- data updates [ADO], batch mode
- batch mode [ADO]
- updating data [ADO], batch mode
ms.assetid: 0cb548e0-fcb4-4c49-98c8-be287911f826
author: rothja
ms.author: jroth
ms.openlocfilehash: b7e4ce2e8928ac7b4225ae58b25c6610c64832f7
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82761250"
---
# <a name="batch-mode"></a>Пакетный режим
Пакетный режим действует, если свойство **LockType** имеет значение **адлоккбатчоптимистик** , а пакетное обновление поддерживается поставщиком. Некоторые параметры типа блокировки недоступны в зависимости от положения курсора. Например, тип пессимистической блокировки недоступен, если для **CursorLocation** задано значение **адусеклиент**. И наоборот, поставщик не может поддерживать оптимистичную блокировку пакетной службы, если расположение курсора находится на сервере. Пакетное обновление следует использовать только с курсором KEYSET или static.  
  
 Метод **UpdateBatch** используется для отправки изменений **набора записей** , хранящихся в буфере копирования, на сервер для обновления источника данных. В следующем разделе будет открыт **набор записей** в пакетном режиме, внесены изменения в буфер копирования, а затем отправлены изменения в источник данных с помощью вызова **UpdateBatch**.  
  
 В этом разделе рассматриваются следующие вопросы.  
  
-   [Отправка обновлений: метод UpdateBatch](../../../ado/guide/data/sending-the-updates-updatebatch-method.md)  
  
-   [Фильтрация обновленных записей](../../../ado/guide/data/filtering-for-updated-records.md)  
  
-   [Работа с ошибками обновлений](../../../ado/guide/data/dealing-with-failed-updates.md)  
  
-   [Обнаружение и разрешение конфликтов](../../../ado/guide/data/detecting-and-resolving-conflicts.md)  
  
-   [Отключение и повторное подключение набора записей](../../../ado/guide/data/disconnecting-and-reconnecting-the-recordset.md)  
  
-   [Обновление результатов объединения JOIN: уникальная таблица](../../../ado/guide/data/updating-joined-results-unique-table.md)
