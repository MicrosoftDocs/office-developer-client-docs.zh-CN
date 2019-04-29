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
  
 **将新的邮件服务添加到配置文件并访问新的邮件服务**
  
调用[IMsgServiceAdmin2:: CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md)。 **CreateMsgServiceEx**执行以下任务: 
  
1. 复制 mapisvc.inf 中的邮件服务的所有相关信息。INF 文件, 为每个提供程序部分创建一个配置文件部分。
    
2. 调用邮件服务的入口点函数**MSGSERVICEENTRY**, 并将_ulContext_参数设置为 MSG_SERVICE_CREATE。 
    
3. 设置和检索邮件服务的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性。
    
 **访问任何新添加的邮件服务**
  
1. 调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)以检索邮件服务表。 
    
2. 调用邮件服务表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册表通知。 
    
3. 当 MAPI 发送 TABLE_ROW_ADDED 通知时, 请在[TABLE_NOTIFICATION](table_notification.md)结构中包含的[SRow](srow.md)结构中查找新添加的邮件服务的条目标识符。 
    

