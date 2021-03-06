---
title: PidLidReminderDelta 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderDelta
api_type:
- COM
ms.assetid: 011d73d0-8b38-4a4e-a56f-92dec451946a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 86a0203f930661452bb143e247c17ef6da8ed436
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315888"
---
# <a name="pidlidreminderdelta-canonical-property"></a>PidLidReminderDelta 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定第一次提醒过期的时间与日历对象的开始时间之间的间隔（以分钟为单位）。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidReminderDelta  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008501  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Reminder  <br/> |
   
## <a name="remarks"></a>备注

必须在日历对象上设置此属性。 对于所有非日历对象，此属性应设置为"0x00000000"并被忽略。 当为定期日历对象的一个实例消除提醒时，此属性的值将用于计算下一个实例的信号时间。 有关[日历对象创建的详细信息，请参阅 [MS- OXOCAL]。](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定电子邮件和其他对象提醒的属性和交互模型。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

