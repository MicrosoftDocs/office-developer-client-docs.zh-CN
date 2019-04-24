---
title: PidLidAppointmentColor 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentColor
api_type:
- COM
ms.assetid: 91147e85-f440-4463-850b-efc9bdbd36d1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1ea0830a06f303da8243f927e4a07cc744951ca9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345435"
---
# <a name="pidlidappointmentcolor-canonical-property"></a>PidLidAppointmentColor 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定在显示日历时要使用的颜色。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptColor  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x00008214  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>注解

此属性指定在显示日历时要使用的颜色。 客户端或服务器应设置此值以实现与旧客户端的向后兼容性。 它可能改为根据[[OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中指定的**关键字**([PidNameKeywords](pidnamekeywords-canonical-property.md)) 属性的值显示日历。 如果设置, 则值必须是下列值之一。
  
|**值**|**Color**|
|:-----|:-----|
|0x00000000  <br/> |无  <br/> |
|0x00000001  <br/> |红色  <br/> |
|0x00000002  <br/> |蓝色  <br/> |
|0x00000003  <br/> |绿色  <br/> |
|0x00000004  <br/> |灰色  <br/> |
|0x00000005  <br/> |橙色  <br/> |
|0x00000006  <br/> |蓝绿  <br/> |
|0x00000007  <br/> |橄榄色  <br/> |
|0x00000008  <br/> |紫色  <br/> |
|0x00000009  <br/> |青色  <br/> |
|0x0000000A  <br/> |黄色  <br/> |
   
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

