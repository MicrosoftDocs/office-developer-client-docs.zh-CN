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
ms.openlocfilehash: 66208b2d31ca379389f3249abf281dd4d040e276
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777125"
---
# <a name="pidlidtodotitle-canonical-property"></a>PidLidToDoTitle 规范属性

  
  
**适用于**： Outlook 
  
包含要合并的待办事项列表中的此消息对象标识的用户并以此来文本。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidToDoTitle  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x000085A4  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>说明

此属性必须设置对任务。 若要指示属性为空，未将此属性设置为零长度字符串中，但而是将其删除。 
  
标记邮件对象和属性不存在，当客户端应**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 的值都写入到此属性。
  
在合并待办事项列表中，如果此属性不存在，则客户端应在待办事项列表中显示此属性时替换**PR_NORMALIZED_SUBJECT**属性的值。 
  
在草稿 message 对象，如果客户端实现发件人标志，此属性应设置为**dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 相同的值。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidTagNormalizedSubject 规范属性](pidtagnormalizedsubject-canonical-property.md)
  
[PidLidFlagRequest 规范属性](pidlidflagrequest-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

