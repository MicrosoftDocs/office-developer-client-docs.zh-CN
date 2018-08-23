---
title: 添加邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1e626714-52dc-4141-9741-4d801f32d294
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6a8b0f8fc8c296fe4022ac28623b83d270472ca3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590692"
---
# <a name="adding-a-message-service"></a>添加邮件服务

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 **配置文件中添加一个新的消息服务和访问新邮件服务**
  
调用[IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md)。 **CreateMsgServiceEx**执行以下任务： 
  
1. 复制所有邮件服务正在 MAPISVC 的相关信息。INF 文件中，创建每个提供程序部分的配置文件一节。
    
2. 调用带有_ulContext_参数设置为 MSG_SERVICE_CREATE 消息服务的入口点函数， **MSGSERVICEENTRY**。 
    
3. 设置和检索邮件服务**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性。
    
 **若要访问任何新添加的消息服务**
  
1. 调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)检索邮件服务表。 
    
2. 调用邮件服务表[IMAPITable::Advise](imapitable-advise.md)方法，以注册表通知。 
    
3. MAPI 时发送 TABLE_ROW_ADDED 通知，包括在[TABLE_NOTIFICATION](table_notification.md)结构[SRow](srow.md)结构中找到的新添加的消息服务的项标识符。 
    

