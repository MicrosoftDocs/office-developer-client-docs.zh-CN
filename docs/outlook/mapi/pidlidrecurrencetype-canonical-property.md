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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315909"
---
# <a name="pidlidrecurrencetype-canonical-property"></a>PidLidRecurrenceType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定定期系列的定期类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidRecurType  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x00008231  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

此属性通过使用下面列出的值之一指定定期系列的定期类型。
  
|**Status**|**Value**|**说明**|
|:-----|:-----|:-----|
|rectypeNone  <br/> |0  <br/> |单个实例约会。  <br/> |
|rectypeDaily  <br/> |1  <br/> |每日定期模式。  <br/> |
|rectypeWeekly  <br/> |双面  <br/> |每周定期模式。  <br/> |
|rectypeMonthly  <br/> |第三章  <br/> |每月定期模式。  <br/> |
|rectypeYearly  <br/> |4  <br/> |每年定期模式。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

