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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a00505b765abdcb7b8fe9d68052774b30bbdf692
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778349"
---
# <a name="pidtagscheduleinfofreebusytentative-canonical-property"></a>PidTagScheduleInfoFreeBusyTentative 规范属性

  
  
**适用于**： Outlook 
  
包含的基块处于暂定忙/闲状态的时间。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_SCHDINFO_FREEBUSY_TENTATIVE  <br/> |
|标识符:  <br/> |0x6852  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>备注

此属性在**PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) 中具有多个值作为值的数目。 每个二进制值表示的月和对应于**PR_SCHDINFO_MONTHS_TENTATIVE**中相同的索引处的值。 **PR_SCHDINFO_MONTHS_TENTATIVE**中的值相同的顺序排序的二进制值。
  
每个二进制值都有一个或多个 4 字节块，以及每个包含前两个字节的开始时间和结束时间-little-endian 格式中的第二个两个字节。 相应月份的第一天的协调世界时 (UTC) 午夜和采用 UTC 的事件的开始时间之间的分钟数的开始时间。 相应月份的第一天的午夜 UTC 和采用 UTC 的事件的结束时间之间的分钟数的结束时间。 4 字节块按升序排序。
  
连续或重叠的时间段合并到一个块作为的开始时间的开始时间的第一个块和作为的最后一个块的结束时间的结束时间。 如果事件跨多个月或年，则事件分为多个块，一个用于每个月。 如果发布范围中没有暂定事件，然后此属性和**PR_SCHDINFO_MONTHS_TENTATIVE**不得设置或者如果已存在，则必须删除。 否则，必须设置此属性。 
  
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
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

