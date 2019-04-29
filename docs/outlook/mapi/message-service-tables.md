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
ms.openlocfilehash: c644e89511033234aa45c5f82738e4c471ef646d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422493"
---
# <a name="message-service-tables"></a>邮件服务表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件服务表包含有关当前配置文件中的邮件服务的信息。 每个 mapi 会话都有一个邮件服务表, 这些会话由 mapi 实现, 并由提供配置支持的特殊用途的客户端应用程序使用。 
  
邮件服务表是静态表。
  
客户端通过调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)方法访问邮件服务表。 
  
以下属性构成了在邮件服务表中设置的必需列:
  
|||
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |
|**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |**PR_SERVICE_DLL_NAME**([PidTagServiceDllName](pidtagservicedllname-canonical-property.md))  <br/> |
|**PR_SERVICE_ENTRY_NAME**([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md))  <br/> |**PR_SERVICE_NAME**([PidTagServiceName](pidtagservicename-canonical-property.md))  <br/> |
|**PR_SERVICE_SUPPORT_FILES**([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md))  <br/> |**PR_SERVICE_UID**([PidTagServiceUid](pidtagserviceuid-canonical-property.md))  <br/> |
   
 **PR_DISPLAY_NAME**是邮件服务和默认的排序关键字列的可显示名称。 
  
 **PR_INSTANCE_KEY**充当表的索引列, 唯一标识行。 
  
 **PR_RESOURCE_FLAGS**描述了邮件服务的功能。 
  
 **PR_SERVICE_DLL_NAME**是包含邮件服务实现的 DLL 的名称。 
  
 **PR_SERVICE_ENTRY_NAME**是符合[MSGSERVICEENTRY](msgserviceentry.md)原型的邮件服务的入口点函数的名称。 
  
 **PR_SERVICE_NAME**是 mapisvc.inf 中的 **[服务]** 部分中的必需条目。 此属性的值永远不会更改或本地化。 **PR_SERVICE_NAME**可用于以编程方式标识邮件服务。 
  
 **PR_SERVICE_SUPPORT_FILES**是必须随邮件服务一起安装的文件的列表。 
  
 **PR_SERVICE_UID**是邮件服务的唯一标识符。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

