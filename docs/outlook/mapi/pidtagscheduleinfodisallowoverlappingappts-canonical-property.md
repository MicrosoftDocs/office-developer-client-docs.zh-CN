---
title: PidTagScheduleInfoDisallowOverlappingAppts 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDisallowOverlappingAppts
api_type:
- COM
ms.assetid: 27978a09-daf7-4a50-927a-96d9c4a97d02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5ead258c056ec2204ddab92e9b99e1b17fe98092
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330084"
---
# <a name="pidtagscheduleinfodisallowoverlappingappts-canonical-property"></a>PidTagScheduleInfoDisallowOverlappingAppts 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果不允许重叠约会，则包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_DISALLOW_OVERLAPPING_APPTS  <br/> |
|标识符:  <br/> |0x686F  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>备注

此属性仅在[PidTagScheduleInfoAutoAcceptAppointments](pidtagscheduleinfoautoacceptappointments-canonical-property.md) PR_SCHDINFO_AUTO_ACCEPT_APPTS (值为 TRUE 时) 才有意义。  TRUE 值表示在自动响应会议请求时，客户端或服务器必须拒绝与以前安排的事件重叠的实例。 FALSE 值或缺少此属性指示必须接受重叠实例。 这不是必需的属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
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

