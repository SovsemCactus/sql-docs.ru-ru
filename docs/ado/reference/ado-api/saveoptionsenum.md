---
title: Савеоптионсенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- SaveOptionsEnum
helpviewer_keywords:
- SaveOptionsEnum enumeration [ADO]
ms.assetid: 59339100-6e29-48d1-aea3-6873796d186b
author: rothja
ms.author: jroth
ms.openlocfilehash: 3423d215fa4a52286509769bb2ac0b75d2283a02
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82755840"
---
# <a name="saveoptionsenum"></a>SaveOptionsEnum
Указывает, следует ли создавать или перезаписывать файл при сохранении из объекта [потока](../../../ado/reference/ado-api/stream-object-ado.md) . Значения могут быть **адсавекреатенотексист** или **адсавекреатеоверврите**.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adSaveCreateNotExist**|1|По умолчанию. Создает новый файл, если файл, указанный в параметре *filename* , еще не существует.|  
|**adSaveCreateOverWrite**|2|Перезаписывает файл данными из текущего открытого объекта **потока** , если файл, указанный параметром *filename* , уже существует. Если файл, указанный параметром *filename* , не существует, создается новый файл.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Эти константы не имеют эквивалентов ADO/WFC.  
  
## <a name="applies-to"></a>Применяется к  
 [Метод SaveToFile](../../../ado/reference/ado-api/savetofile-method.md)
