---
title: PidTagScheduleInfoMonthsAway 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoMonthsAway
api_type:
- COM
ms.assetid: 282a8ba1-b786-4d17-b6c5-17e935e59a6b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 90df272a70fd4133a780f205c93b42f26ed1ae96
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303407"
---
# <a name="pidtagscheduleinfomonthsaway-canonical-property"></a>PidTagScheduleInfoMonthsAway 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含在忙/闲邮件中存在类型为外出 (OOF) 的忙/闲数据的月份列表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_MONTHS_OOF  <br/> |
|标识符:  <br/> |0x6855  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |闲/忙  <br/> |
   
## <a name="remarks"></a>注解

此属性的格式、计算和约束与**PR_SCHDINFO_FREEBUSY_TENTATIVE** (PidTagScheduleInfoFreeBusyTentative) 的格式、计算和约束相同, 但引用在关联的[](pidtagscheduleinfofreebusytentative-canonical-property.md)上标记为外出 (OOF) 的约会。calendar 对象。
  
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

