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
ms.openlocfilehash: 6fa0579dcd98a0d819e58e62d8a42cb2972a9d1e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359757"
---
# <a name="pidtagscheduleinfomonthstentative-canonical-property"></a>PidTagScheduleInfoMonthsTentative 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含忙/闲邮件中标记为 "暂定" 的月份。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_MONTHS_TENTATIVE  <br/> |
|标识符:  <br/> |0x6851  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |闲/忙  <br/> |
   
## <a name="remarks"></a>注解

此属性中的值的数目必须介于零和发布区域所覆盖的月数之间, 这是**PR_FREEBUSY_PUBLISH_START** ([PidTagFreeBusyPublishStart](pidtagfreebusypublishstart-canonical-property.md)) 和 PR_FREEBUSY_PUBLISH_END 之间的时间段。 ****([PidTagFreeBusyPublishEnd](pidtagfreebusypublishend-canonical-property.md)) 属性。
  
此属性中的每个值都有在其中编码的月份和年份。 这是通过使用表达式 "year × 16 + 月" 计算的, 其中的年和月基于公历。 值按升序排序, 并以小字节序格式进行编码。 如果某个事件分布在多个月或多年, 则发布区域中的每个月都必须有一个值。 如果发布区域中没有暂定事件, 则不能设置此属性和**PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)), 如果它们已经存在, 则必须将其删除。 否则, 必须设置此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> 发布用户或资源的可用性。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

