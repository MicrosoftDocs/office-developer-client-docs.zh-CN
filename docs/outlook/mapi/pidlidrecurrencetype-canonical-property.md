---
title: PidLidRecurrenceType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRecurrenceType
api_type:
- COM
ms.assetid: 81ad2e8a-661f-4fc7-bee4-848db3285e31
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a0ea0dfe236341815fe94fb570908d7034fc83e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389174"
---
# <a name="pidlidrecurrencetype-canonical-property"></a>PidLidRecurrenceType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定定期系列的定期类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidRecurType  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008231  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>说明

此属性使用下列值之一指定定期系列的定期类型。
  
|**Status**|**值**|**说明**|
|:-----|:-----|:-----|
|rectypeNone  <br/> |0  <br/> |单实例约会。  <br/> |
|rectypeDaily  <br/> |1  <br/> |每天定期模式。  <br/> |
|rectypeWeekly  <br/> |2  <br/> |每周定期模式。  <br/> |
|rectypeMonthly  <br/> |3  <br/> |每月定期模式。  <br/> |
|rectypeYearly  <br/> |4  <br/> |每年的定期模式。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

