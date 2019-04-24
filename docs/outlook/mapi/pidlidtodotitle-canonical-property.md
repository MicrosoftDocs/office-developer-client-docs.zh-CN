---
title: PidLidToDoTitle 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToDoTitle
api_type:
- COM
ms.assetid: 94cf031f-4c78-441d-9c01-55905b4974e0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7ed69d9bab84a5c572026bb9480249c1212e3376
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339940"
---
# <a name="pidlidtodotitle-canonical-property"></a>PidLidToDoTitle 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用户 specifiable 文本, 用于在合并的待办工作列表中标识此 message 对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidToDoTitle  <br/> |
|属性集:  <br/> |PSETID_Common  <br/> |
|长 ID (盖子):  <br/> |0x000085A4  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

不得对任务设置此属性。 若要指示一个空属性, 请不要将此属性设置为零长度字符串, 而是将其删除。 
  
标记邮件对象时, 如果该属性不存在, 客户端应将**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 的值写入该属性。
  
在合并的待办任务列表中, 如果该属性不存在, 客户端应在待办任务列表中显示此属性时替换**PR_NORMALIZED_SUBJECT**属性的值。 
  
在草稿邮件对象上, 如果客户端实现发件人标志, 则应将此属性设置为与**dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 相同的值。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用
    
[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidTagNormalizedSubject 规范属性](pidtagnormalizedsubject-canonical-property.md)
  
[PidLidFlagRequest 规范属性](pidlidflagrequest-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

