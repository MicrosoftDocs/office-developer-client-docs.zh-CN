---
title: 删除邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 346608d7-f7de-497e-9852-4d4d7696177e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 34d9d6d428f39765e739ce856f3666d07b457d52
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774769"
---
# <a name="deleting-a-message-service"></a>删除邮件服务

  
  
**适用于**： Outlook 
  
 **从配置文件中删除的消息服务**
  
1. 调用**IMAPISession::GetMsgServiceTable**访问邮件服务表。 
    
2. 找到消息服务的行，并将其**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列_lpuid_参数中传递给[IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md)。 
    
 **DeleteMsgService** _ulContext_参数设置为 MSG_SERVICE_DELETE 调用消息服务的入口点函数。 消息服务会执行任何清理任务在此时之前从配置文件中删除这些空格。 
  

