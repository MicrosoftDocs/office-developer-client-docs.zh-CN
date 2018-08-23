---
title: PidLidBusyStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidBusyStatus
api_type:
- COM
ms.assetid: 50c91fe6-2a61-4348-a16d-fd5c501b0715
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1ea252f8333bf39d391b8d99b768c9c3fa8e57ba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568733"
---
# <a name="pidlidbusystatus-canonical-property"></a>PidLidBusyStatus 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
代表约会的用户的可用性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidBusyStatus  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008205  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

此属性指定对象所述的事件的用户的可用性，并且必须为下面指定的值之一。
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |用户可用。  <br/> |
|0x00000001  <br/> |用户可以安排一个暂定事件。  <br/> |
|0x00000002  <br/> |用户正忙。  <br/> |
|0x00000003  <br/> |用户不在办公室。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

