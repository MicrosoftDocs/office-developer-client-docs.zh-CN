---
title: PidLidReminderFileParameter 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderFileParameter
api_type:
- COM
ms.assetid: 1009f0ea-6f35-484d-b04d-5b6e844c14dd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 42eec18c74005e586657482ef6634669c489314d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360099"
---
# <a name="pidlidreminderfileparameter-canonical-property"></a>PidLidReminderFileParameter 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定当该对象的提醒过期时, 客户端应播放的声音的文件名。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidReminderFileParam  <br/> |
|属性集:  <br/> |PSETID_Common  <br/> |
|长 ID (盖子):  <br/> |0x0000851F  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |提醒  <br/> |
   
## <a name="remarks"></a>注解

如果此属性不存在, 则客户端可以使用默认值。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定用于电子邮件和其他对象提醒的属性和交互模型。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

