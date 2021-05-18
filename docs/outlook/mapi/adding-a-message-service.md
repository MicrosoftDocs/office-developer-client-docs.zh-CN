---
title: 添加邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1e626714-52dc-4141-9741-4d801f32d294
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 30cbe49eae7b4a232efb544c7a508a36b326c6b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407233"
---
# <a name="adding-a-message-service"></a>添加邮件服务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **向配置文件添加新邮件服务并访问新邮件服务**
  
调用 [IMsgServiceAdmin2：：CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md)。 **CreateMsgServiceEx** 执行以下任务： 
  
1. 复制 MAPISVC 中邮件服务的所有相关信息。INF 文件，创建每个提供程序节的配置文件部分。
    
2. 调用邮件服务的入口点函数 **MSGSERVICEENTRY，ulContext** 参数设置为MSG_SERVICE_CREATE。 
    
3. 使用[PidTagServiceUid](pidtagserviceuid-canonical-property.md)  PR_SERVICE_UID (和检索邮件) 。
    
 **访问任何新添加的邮件服务**
  
1. 调用 [IMsgServiceAdmin：：GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) 以检索邮件服务表。 
    
2. 调用消息服务表的 [IMAPITable：：Advise](imapitable-advise.md) 方法以注册表通知。 
    
3. 当 MAPI 发送TABLE_ROW_ADDED通知时，在邮件结构中包含的[SRow](srow.md)结构中找到新添加的邮件服务的[TABLE_NOTIFICATION标识符。](table_notification.md) 
    

