---
title: PidTagScheduleInfoFreeBusyTentative 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyTentative
api_type:
- COM
ms.assetid: 28453d29-30c5-405b-84d2-5bb5f281756c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 18bc41d9038113b5b813f1cfd02d90b8e982703c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359771"
---
# <a name="pidtagscheduleinfofreebusytentative-canonical-property"></a>PidTagScheduleInfoFreeBusyTentative 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含忙/闲状态为 "暂定" 的时间段。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_FREEBUSY_TENTATIVE  <br/> |
|标识符:  <br/> |0x6852  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |闲/忙  <br/> |
   
## <a name="remarks"></a>注解

此属性的值与**PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) 中的值数相同。 每个二进制值表示一个月, 并与**PR_SCHDINFO_MONTHS_TENTATIVE**中同一索引处的值相对应。 二进制值按与**PR_SCHDINFO_MONTHS_TENTATIVE**中的值相同的顺序进行排序。
  
每个二进制值具有一个或多个4字节块, 每个块都包含以小字节结尾格式的前两个字节中的开始时间和以秒为单位的前两个字节的结束时间。 "开始时间" 是一个月的第一天与事件的开始时间之间的协调世界时 (utc) 之间的分钟数和 UTC 的开始时间。 结束时间是一个月的第一天 (utc 时间) 与事件的结束时间之间的午夜 (utc) 之间的分钟数。 4字节块按升序排列。
  
连续或重叠的时间块合并为一个块, 其开始时间为第一个块的开始时间和结束时间为最后一个块的结束时间。 如果一个事件分布在多个月或几年, 则该事件被拆分为多个块, 每个月一个。 如果发布区域中没有暂定事件, 则不能设置此属性和**PR_SCHDINFO_MONTHS_TENTATIVE** , 如果它们已经存在则必须删除。 否则, 必须设置此属性。 
  
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

