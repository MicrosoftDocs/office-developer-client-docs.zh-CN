---
title: 邮件服务表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b93ab837-3918-4427-b013-bedc6f5276e4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 569c1bd7ee2f4ac6c321f234be2954a57715549b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576665"
---
# <a name="message-service-tables"></a>邮件服务表

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
邮件服务表包含有关当前配置文件中的消息服务的信息。 对于每个 MAPI 会话，由 MAPI 实现并供提供配置支持的特殊用途客户端应用程序没有邮件服务的一个表。 
  
邮件服务表是一个静态表。
  
客户端调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)方法来访问邮件服务表。 
  
以下属性构成设置消息服务表中所需的列：
  
|||
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |
|**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |**PR_SERVICE_DLL_NAME**([PidTagServiceDllName](pidtagservicedllname-canonical-property.md))  <br/> |
|**PR_SERVICE_ENTRY_NAME**([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md))  <br/> |**PR_SERVICE_NAME**([PidTagServiceName](pidtagservicename-canonical-property.md))  <br/> |
|**PR_SERVICE_SUPPORT_FILES**([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md))  <br/> |**PR_SERVICE_UID**([PidTagServiceUid](pidtagserviceuid-canonical-property.md))  <br/> |
   
 **PR_DISPLAY_NAME**是可显示名称的消息服务和默认排序键列。 
  
 **PR_INSTANCE_KEY**充当索引列的表中，用于唯一地标识行。 
  
 **PR_RESOURCE_FLAGS**描述消息服务的功能。 
  
 **PR_SERVICE_DLL_NAME**是包含消息服务实现的 DLL 的名称。 
  
 **PR_SERVICE_ENTRY_NAME**是符合[MSGSERVICEENTRY](msgserviceentry.md)原型的消息服务的入口点函数的名称。 
  
 **PR_SERVICE_NAME**是必的填项 **[服务]** 节中 MAPISVC.INF。 将永远不会更改此属性的值，或为其本地化。 **PR_SERVICE_NAME**可用于以编程方式标识邮件服务。 
  
 **PR_SERVICE_SUPPORT_FILES**是必须与消息服务安装文件的列表。 
  
 **PR_SERVICE_UID**是邮件服务的唯一标识符。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

