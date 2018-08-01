---
title: PidLidTaskRecurrence 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskRecurrence
api_type:
- COM
ms.assetid: e675bfdd-7598-45f3-a5aa-23b4734670dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 29b35250a3cbbee876338ca2366726b2dd14f957
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777105"
---
# <a name="pidlidtaskrecurrence-canonical-property"></a>PidLidTaskRecurrence 规范属性

  
  
**适用于**： Outlook 
  
包含提供有关周期性任务信息的 RecurrencePattern 结构。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskRecur  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008116  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>说明

有关如何创建并指定一个 RecurrencePattern 结构的信息，请参阅[创建简单的定期任务项](how-to-create-a-simple-recurrent-task-item.md)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象。
    
[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定属性和电子邮件和其他对象提醒的交互模型。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

