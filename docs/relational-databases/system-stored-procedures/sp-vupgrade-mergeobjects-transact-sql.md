---
title: sp_vupgrade_mergeobjects (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_vupgrade_mergeobjects
- sp_vupgrade_mergeobjects_TSQL
helpviewer_keywords:
- sp_vupgrade_mergeobjects
ms.assetid: 73257c2e-cc4c-48e7-9d66-7ef045bdd4f5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ec503a73e6600674e997e47670f84973236a59c2
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82808849"
---
# <a name="sp_vupgrade_mergeobjects-transact-sql"></a>sp_vupgrade_mergeobjects (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Повторно создает триггеры конкретных статей, хранимые процедуры и представления, с помощью которых отслеживаются и вносятся изменения данных для репликации слиянием. Эту процедуру следует выполнять в следующих случаях.  
  
-   Если объект, необходимый для репликации, случайно был удален.  
  
-   Если применяется обновление, например исправление, для которого требуется изменить один или несколько объектов репликации. После применения обновления процедуру следует выполнить на каждом узле.  
  
 Выполнение этой хранимой процедуры не требует повторной инициализации подписок. Эта процедура не является обязательной при установке пакета обновления или при обновлении до новой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_vupgrade_mergeobjects [ [@login = ] 'login' ]  
    [ , [ @password = ] 'password' ]  
    [ , [ @security_mode = ] security_mode ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @login = ] 'login'`— Это имя входа системного администратора, используемое при создании новых системных объектов в базе данных распространителя. Аргумент *login* имеет тип **sysname** и значение по умолчанию NULL. Этот параметр не требуется, если *security_mode* имеет значение **1**, которое является проверкой подлинности Windows.  
  
`[ @password = ] 'password'`Пароль системного администратора, используемый при создании новых системных объектов в базе данных распространителя. Аргумент *Password* имеет тип **sysname**и значение по умолчанию **""** (пустая строка). Этот параметр не требуется, если *security_mode* имеет значение **1**, которое является проверкой подлинности Windows.  
  
`[ @security_mode = ] 'security_mode'`Режим безопасности входа, используемый при создании новых системных объектов в базе данных распространителя. *security_mode* имеет **бит** со значением по умолчанию **1**. Если значение **равно 0**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет использоваться проверка подлинности. Если значение равно **1**, будет использоваться проверка подлинности Windows. [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Примечания  
 **sp_vupgrade_mergeobjects** используется только для репликации слиянием.  
  
## <a name="permissions"></a>Разрешения  
 Необходимо членство в предопределенной роли сервера **sysadmin** .  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры репликации &#40;&#41;Transact-SQL](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [Обновление реплицируемых баз данных](../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
  
