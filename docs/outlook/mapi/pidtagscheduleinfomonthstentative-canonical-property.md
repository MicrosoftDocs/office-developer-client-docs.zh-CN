---
title: PidTagScheduleInfoMonthsTentative 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoMonthsTentative
api_type:
- COM
ms.assetid: 3179442c-6499-464a-93af-eb0a7a5b0d30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 78bb5114b78142ce18d3f83c34795b72910c87a2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573710"
---
# <a name="pidtagscheduleinfomonthstentative-canonical-property"></a>PidTagScheduleInfoMonthsTentative 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含标记暂定忙/闲信息消息中的月份。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_MONTHS_TENTATIVE  <br/> |
|标识符：  <br/> |0x6851  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>注解

此属性中的值数必须介于零和涵盖了发布的范围，这是**PR_FREEBUSY_PUBLISH_START** ([PidTagFreeBusyPublishStart](pidtagfreebusypublishstart-canonical-property.md)) 和**PR_FREEBUSY_PUBLISH_END 之间的时间段的月数之间**([PidTagFreeBusyPublishEnd](pidtagfreebusypublishend-canonical-property.md)) 属性。
  
此属性中，每个值都有月份和年份中编码。 这是通过使用表达式"年 × 16 + 月"年和月基于公历日历上计算得出。 值以升序排序，并以-little-endian 格式编码。 如果事件跨多个月或多个年，必须有一个月发布的范围中的每个值。 如果发布范围中没有暂定事件，然后此属性和**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 不能设置或者如果已存在，则必须删除。 否则，必须设置此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> 发布的用户或资源的可用性。
    
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

