---
title: Фильтрация данных перед загрузкой (надстройка MDS для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9e30eae0-776b-4a09-aac3-0c0249d92ca5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c864e95a075477b80bdbbe06912be37bba33fadf
ms.sourcegitcommit: f71e523da72019de81a8bd5a0394a62f7f76ea20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84961148"
---
# <a name="filter-data-before-loading-mds-add-in-for-excel"></a>Фильтрация данных перед их загрузкой (надстройка MDS для Excel)
  В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] данные отфильтруются, если требуется ограничить размер или область данных, загружаемых в Excel.  
  
## <a name="prerequisites"></a>Предварительные условия  
 Для выполнения этой процедуры:  
  
-   Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .  
  
### <a name="to-filter-data-before-loading"></a>Фильтрация данных перед загрузкой  
  
1.  Откройте Excel и на вкладке **Основные данные** установите соединение с репозиторием MDS. Дополнительные сведения см. в разделе [Соединение с репозиторием MDS (надстройка MDS для Excel)](connect-to-an-mds-repository-mds-add-in-for-excel.md).  
  
2.  На панели **Обозреватель основных данных** выберите модель и версию. Заполняется список сущностей.  
  
    -   Если панель **Обозреватель основных данных** не видна, в группе **Соединение и загрузка** нажмите **Показать обозреватель**.  
  
    -   Если панель **Обозреватель основных данных** отключена, то причина этого заключается в том, что существующий лист уже содержит данные, управляемые MDS. Чтобы включить эту панель, откройте новый лист.  
  
3.  На панели **Обозреватель основных данных** в списке сущностей выберите сущность, которую нужно отфильтровать.  
  
4.  На ленте в группе **Подключение и загрузка** нажмите кнопку **Фильтр**.  
  
5.  В диалоговом окне **Фильтр** выберите атрибуты (столбцы) для отображения, определите их порядок и при необходимости отфильтруйте данные так, чтобы возвращалось меньшее число строк. На панели **Сводка** можно увидеть, сколько данных будет возвращено. Дополнительные сведения см. в разделе [Диалоговое окно "Фильтр" (надстройка MDS для Excel)](filter-dialog-box-mds-add-in-for-excel.md).  
  
6.  Нажмите кнопку **Загрузить данные**. Лист заполняется данными, управляемыми MDS.  
  
    > [!NOTE]  
    >  -   В Excel загружается только первый миллион элементов.  
    > -   В столбцах, которые являются ограниченными списками (атрибутами на основе домена), загружается только первая тысяча значений.  
  
## <a name="next-steps"></a>Next Steps  
 [Публикация данных из Excel в службах MDS &#40;надстройка MDS для Excel&#41;](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a>См. также:  
 [Загрузка надстройка MDS для Excel &#40;данных&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md)   
 [Диалоговое окно "фильтр" &#40;надстройка MDS для Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md)   
 [Переупорядочение столбцов (надстройка MDS для Excel)](reorder-columns-mds-add-in-for-excel.md)  
  
  
