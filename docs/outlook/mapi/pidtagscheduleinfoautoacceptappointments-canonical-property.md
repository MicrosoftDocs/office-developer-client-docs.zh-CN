---
title: PidTagScheduleInfoAutoAcceptAppointments 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoAutoAcceptAppointments
api_type:
- COM
ms.assetid: 79505b29-2706-472b-b084-ab74be7b3405
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6fe724d70ac86b1c51e72f243ef9255dd452be9c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330091"
---
# <a name="pidtagscheduleinfoautoacceptappointments-canonical-property"></a>PidTagScheduleInfoAutoAcceptAppointments 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果客户端或服务器应自动响应与会者或资源的所有会议请求, 则该参数为 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_AUTO_ACCEPT_APPTS  <br/> |
|标识符:  <br/> |0x686D  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |闲/忙  <br/> |
   
## <a name="remarks"></a>注解

响应时, 响应必须是可接受的, 除非**PR_SCHDINFO_DISALLOW_RECURRING_APPTS** ([PidTagScheduleInfoDisallowRecurringAppts](pidtagscheduleinfodisallowrecurringappts-canonical-property.md)) 或 PR_SCHDINFO_DISALLOW_ 指定的其他约束**满足 OVERLAPPING_APPTS** ([PidTagScheduleInfoDisallowOverlappingAppts](pidtagscheduleinfodisallowoverlappingappts-canonical-property.md)) 属性。 如果值为 FALSE 或缺少此属性, 则表示客户端或服务器不能自动接受会议请求。 这不是必需的属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
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

