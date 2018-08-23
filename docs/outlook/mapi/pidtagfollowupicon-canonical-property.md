---
title: PidTagFollowupIcon 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFollowupIcon
api_type:
- HeaderDef
ms.assetid: 374cef41-141a-491b-8dd1-eaf1a2044204
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8fa96736b5404d84c6ab48851b916c5ab987ae2a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593919"
---
# <a name="pidtagfollowupicon-canonical-property"></a>PidTagFollowupIcon 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定消息对象的标志的颜色。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FOLLOWUP_ICON  <br/> |
|标识符：  <br/> |0x1095  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |重命名邮件文件夹  <br/> |
   
## <a name="remarks"></a>注解

此属性必须存在除非**PR_FLAG_STATUS** ([PidTagFlagStatus](pidtagflagstatus-canonical-property.md)) 属性的值设置为"followupFlagged"，或 message 对象是会议相关对象。 此属性不应存在对任务对象。 当在其他消息对象上设置时，此属性必须设置为下列值之一。
  
|**数值**|**名称**|**说明**|
|:-----|:-----|:-----|
|不存在  <br/> |不适用  <br/> |无颜色  <br/> |
|1  <br/> |followupIcon1  <br/> |紫色标志  <br/> |
|2  <br/> |followupIcon2  <br/> |橙色标志  <br/> |
|3  <br/> |followupIcon3  <br/> |绿色标志  <br/> |
|4  <br/> |followupIcon4  <br/> |黄色标志  <br/> |
|5  <br/> |followupIcon5  <br/> |蓝色标志  <br/> |
|6  <br/> |followupIcon6  <br/> |红色标志  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

