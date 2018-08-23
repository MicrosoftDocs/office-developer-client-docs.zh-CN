---
title: PidLidTaskResetReminder 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskResetReminder
api_type:
- COM
ms.assetid: f6da69ff-a913-4a65-bb07-8ad3c5685e5e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e16c1b46b5a8181b1225c706dbed6cd1bb3f486f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583174"
---
# <a name="pidlidtaskresetreminder-canonical-property"></a>PidLidTaskResetReminder 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示以后的定期任务实例是否需要提醒，即使**dispidReminderSet** ([PidLidReminderSet](pidlidreminderset-canonical-property.md)) 为 FALSE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskResetReminder  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008107  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

任务的提醒消除，并且否则设置为 FALSE 时，此值设置为 TRUE。 如果保留未设置，则假定默认值为 FALSE。
  
如指定[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)， **dispidReminderSet**属性指示是否将提醒设置任务。 但是，此属性仅指示一项任务的提醒的状态。 不能使用它来确定定期任务的未来实例是否需要提醒。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象。
    
[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定属性和电子邮件和其他对象提醒的交互模型。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidLidReminderSet 规范属性](pidlidreminderset-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

