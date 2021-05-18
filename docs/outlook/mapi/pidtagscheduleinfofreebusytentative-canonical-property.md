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
  
包含忙/闲状态暂定的时间块。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_FREEBUSY_TENTATIVE  <br/> |
|标识符:  <br/> |0x6852  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>备注

此属性具有与[PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md) PR_SCHDINFO_MONTHS_TENTATIVE (中的值数) 。  每个二进制值表示一个月，对应于中位于同一索引 **PR_SCHDINFO_MONTHS_TENTATIVE。** 二进制值按与值相同的顺序进行排序，如 PR_SCHDINFO_MONTHS_TENTATIVE **。**
  
每个二进制值具有一个或多个 4 字节块，每个二进制值包含以小尾数格式表示的两个字节的开始时间和后两个字节的结束时间。 开始时间是当月第一天的午夜协调世界时 (UTC) 与事件开始时间之间的分钟数（UTC）。 结束时间是一个月的第一天的午夜 UTC 与事件结束时间之间的分钟数（UTC）。 4 字节块按升序排序。
  
连续或重叠的时间块合并为一个块，将开始时间作为第一个块的开始时间，将结束时间合并为最后一个块的结束时间。 如果事件跨多个月或年分布，则事件将拆分为多个块，每月一个块。 如果发布范围中没有任何暂定事件，则不得设置此属性PR_SCHDINFO_MONTHS_TENTATIVE或必须删除它们（如果它们已经存在）。 否则，必须设置此属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> 发布用户或资源的可用性。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

