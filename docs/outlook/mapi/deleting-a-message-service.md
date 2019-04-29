---
title: 删除邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 346608d7-f7de-497e-9852-4d4d7696177e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 27c20242417e51886ab184b1cc87d6ebb185e4bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428121"
---
# <a name="deleting-a-message-service"></a>删除邮件服务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **从配置文件中删除邮件服务**
  
1. 调用**IMAPISession:: GetMsgServiceTable**以访问邮件服务表。 
    
2. 找到邮件服务的行, 并将_lpuid_参数中的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列传递给[IMsgServiceAdmin::D eletemsgservice](imsgserviceadmin-deletemsgservice.md)。 
    
 **DeleteMsgService**调用邮件服务的入口点函数, 并将_ulContext_参数设置为 MSG_SERVICE_DELETE。 在从配置文件中删除所有任务之前, 邮件服务将执行任何清除任务。 
  

