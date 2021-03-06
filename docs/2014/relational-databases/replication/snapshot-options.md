---
title: Изменение параметров инициализации моментальных снимков для репликации SQL | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- snapshot replication [SQL Server], options
- snapshots [SQL Server replication], options
ms.assetid: 759fab42-66c7-4541-a7a3-bb6fb868493c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 946d9035730512a626e710b1140a1ba01290908a
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85055642"
---
# <a name="modify-snapshot-initialization-options-for-sql-replication"></a>Изменение параметров инициализации моментальных снимков для репликации SQL

В этой статье описывается, как изменить ряд параметров при [инициализации подписки с помощью моментального снимка](initialize-a-subscription-with-a-snapshot.md).

## <a name="snapshot-format"></a>Формат моментальных снимков
  Укажите формат моментального снимка на странице **моментальный снимок** диалогового окна ** \<Publication> Свойства публикации —** . Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](publish/view-and-modify-publication-properties.md).  

1.  На странице **моментальный снимок** диалогового окна **свойства \<Publication> публикации —** выберите **собственный SQL Server — все подписчики должны быть серверами, на которых работает SQL Server** , или **обязательным символом, если издатель или подписчик не работает SQL Server**. 

    > [!NOTE]  
    >  Рекомендуется выбирать собственный формат всегда, кроме тех случаев, когда публикация должна поддерживать подписки на базу данных [!INCLUDE[ssEW](../../../includes/ssew-md.md)] или базу данных, отличную от базы данных[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .    
1.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

## <a name="snapshot-folder-locations"></a>Расположение папки моментальных снимков

### <a name="default-snapshot-location"></a>Расположение моментального снимка по умолчанию
Укажите расположение моментальных снимков по умолчанию (SQL Server Management Studio) укажите расположение моментальных снимков по умолчанию на странице **папки моментальных снимков** мастера настройки распространителя. Дополнительные сведения см. в статье [Настройка публикации и распространения](configure-publishing-and-distribution.md). При создании публикации на сервере, не настроенном в качестве распространителя, задайте местоположение моментальных снимков по умолчанию на странице **Папка моментальных снимков** мастера создания публикаций. Дополнительные сведения об использовании мастера см. в статье [Создание публикации](publish/create-a-publication.md).  
  
 Измените расположение моментальных снимков по умолчанию на странице **Издатели** диалогового окна **Свойства распространителя — \<Distributor> ** . Дополнительные сведения см. в статье [Просмотр и изменение свойств издателя и распространителя](view-and-modify-distributor-and-publisher-properties.md). Задайте папку моментальных снимков для каждой публикации в диалоговом окне **Свойства публикации — \<Publication> ** . Дополнительные сведения см. в статье [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).  
  
#### <a name="modify-the-default-snapshot-location"></a>Изменение местоположения моментальных снимков по умолчанию  
  
1.  На странице **Издатели** диалогового окна **Свойства распространителя — \<Distributor> ** нажмите кнопку свойств (..**.**) для издателя, для которого нужно изменить расположение моментальных снимков по умолчанию.    
2.  В диалоговом окне **свойства \<Publisher> издателя —** введите значение для свойства **Папка моментальных снимков по умолчанию** .

    > [!NOTE]  
    >  Агент моментальных снимков должен иметь разрешения на запись в указанный каталог, а агент распространителя или агент слияния должен иметь разрешения на чтение из этого каталога. Если используются подписки по запросу, необходимо указать UNC-путь общего каталога, например \\\computername\snapshot. Дополнительные сведения см. [в разделе Защита папки моментальных снимков](security/secure-the-snapshot-folder.md).    
1.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  

### <a name="alternate-snapshot-location"></a>Альтернативное расположение моментального снимка
  Укажите альтернативное расположение моментального снимка на странице **моментальный снимок** диалогового окна ** \<Publication> Свойства публикации —** . Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](publish/view-and-modify-publication-properties.md). 

  
#### <a name="specify-an-alternate-snapshot-location"></a>Укажите альтернативное расположение моментального снимка  
  
1.  На странице **моментальный снимок** диалогового окна **свойства \<Publication> публикации —** :    
    1.  Выберите **Поместить файлы в следующую папку**, затем нажмите кнопку **Обзор** , чтобы перейти в каталог, или введите путь к каталогу, в который должны сохраняться файлы моментальных снимков.    

        > [!NOTE]  
        >  Агент моментальных снимков должен иметь разрешения на запись в указанный каталог, а агент распространителя или агент слияния должен иметь разрешения на чтение из этого каталога. Если используются подписки по запросу, необходимо указать UNC-путь общего каталога, например \\\computername\snapshot. Дополнительные сведения см. [в разделе Защита папки моментальных снимков](security/secure-the-snapshot-folder.md).    
    а.  Снимите флажок **Поместить файлы в папку по умолчанию** , если не требуется, чтобы файлы были помещены в оба расположения.    
     Для сжатия файлов моментальных снимков выберите **Сжать файлы моментальных снимков в этом расположении**. Сжатие обычно используется для узкополосных подключений и для альтернативных расположений моментальных снимков на сменных носителях, таких, как компакт-диски.    
1.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]   


## <a name="compress-snapshot-files"></a>Сжатие файлов моментальных снимков
Укажите, что файлы следует сжимать, на странице **моментальный снимок** диалогового окна ** \<Publication> Свойства публикации —** . Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](publish/view-and-modify-publication-properties.md).  
  
1.  На странице **моментальный снимок** диалогового окна **свойства \<Publication> публикации —** :  
  
    1.  Выберите **Поместить файлы в следующую папку**, затем нажмите кнопку **Обзор** , чтобы перейти в каталог, или введите путь к каталогу, в который должны сохраняться файлы моментальных снимков.    
        > [!NOTE]  
        >  Агент моментальных снимков должен иметь разрешения на запись в указанный каталог, а агент распространителя или агент слияния должен иметь разрешения на чтение из этого каталога. Если используются подписки по запросу, необходимо указать UNC-путь общего каталога, например \\\computername\snapshot. Дополнительные сведения см. в статье [Организация безопасности папки моментальных снимков](security/secure-the-snapshot-folder.md).  
  
    2.  Снимите флажок **Поместить файлы в папку по умолчанию** , если не требуется, чтобы файлы были помещены в оба расположения.    
        > [!NOTE]  
        >  Если данный флажок установлен, файлы, хранящиеся в папке по умолчанию, не сжимаются. Сжатые файлы можно хранить только в альтернативной папке, указанной на предыдущем шаге.    
2.  Выберите **Выполнять сжатие файлов моментальных снимков в этой папке**.    
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

## <a name="execute-scripts-before-and-after-snapshot-is-applied"></a>Выполнение скриптов до и после применения моментального снимка

 Можно указать скрипты для выполнения на подписчике до и после применения моментального снимка. Скрипты могут использоваться по различным причинам, таким как создание учетных имен и схем (владельцы объекта) на каждом подписчике.  
  
 Вы указываете размещение файла для каждого скрипта, и агент моментальных снимков копирует файлы скриптов в текущую папку моментальных снимков при каждой обработке моментального снимка. При применении моментального снимка агент распространителя или агент слияния запускает скрипт, предшествующий моментальному снимку, перед любым из скриптов реплицируемых объектов. Агент распространителя или агент слияния запускает скрипт, следующий за моментальным снимком, после применения всех других скриптов реплицируемых объектов и применения данных. После того как применение моментального снимка завершено и файлы скриптов успешно выполнены, файлы скриптов удаляются из рабочего каталога на подписчике.  
  
 Скрипт запускается при помощи служебной программы **sqlcmd** . До развертывания скрипта запустите его с помощью **sqlcmd** , чтобы убедиться, что он выполняется должным образом. Содержимое скриптов, которые выполняются до и после применения моментального снимка, должно быть повторяемым. Например, если вы создаете таблицу в скрипте, необходимо сначала проверить ее существование и предпринять соответствующее действие, если таблица существует. Скрипт должен быть повторяемым, потому что, если необходимо повторно инициализировать подписку, для которой уже был применен скрипт, скрипт будет применен повторно, когда новый моментальный снимок будет применяться в процессе повторной инициализации.  
  
 При сжатии файла моментального снимка (посредством его помещения в CAB-файл [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) скрипты так же сжимаются и помещаются в CAB-файл. После того как сжатый файл моментального снимка передан подписчику и распакован в рабочий каталог на подписчике, выполняются все скрипты, помеченные как скрипты, предшествующие моментальному снимку. Аналогично любой скрипт, выполняющийся после моментального снимка, распаковывается и выполняется на подписчике как последний шаг в применении моментального снимка.  

### <a name="execute-a-script-before-or-after-a-snapshot-is-applied"></a>Выполнение скрипта до или после применения моментального снимка  
 Укажите необязательный скрипт для выполнения до или после применения моментального снимка на странице **моментальный снимок** диалогового окна ** \<Publication> Свойства публикации —** . Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](publish/view-and-modify-publication-properties.md).  


1.  На странице **моментальный снимок** диалогового окна **свойства \<Publication> публикации —** :    
    -   Чтобы указать скрипт для выполнения до применения моментального снимка, щелкните **Обзор** для перехода к скрипту или введите путь к скрипту в текстовом поле **Перед применением моментального снимка выполнить этот скрипт** . 
   
        > [!NOTE]  
        >  У агента распространителя или агента слияния должны быть разрешения на чтение в указанном каталоге. Если используются подписки по запросу, следует указать общий каталог в формате UNC-пути, например \\\computername\scripts\myscript.sql.    
    -   Чтобы указать скрипт для выполнения после применения моментального снимка, щелкните **Обзор** для перехода к скрипту или введите путь к скрипту в текстовом поле **После применения моментального снимка выполнить этот скрипт** .    
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
  
