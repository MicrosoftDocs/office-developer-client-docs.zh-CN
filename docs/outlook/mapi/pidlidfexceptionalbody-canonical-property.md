---
title: PidLidFExceptionalBody 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFExceptionalBody
api_type:
- COM
ms.assetid: 327516e8-ed3f-40fc-9604-03a70aecef5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7653d7a56302deaad75443746ff7e83834af260f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571358"
---
# <a name="pidlidfexceptionalbody-canonical-property"></a>PidLidFExceptionalBody 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示例外嵌入对象具有一个不同的定期 calendar 对象的主体的消息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFExceptionalBody  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008206  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

如果此属性的值为 TRUE，然后例外嵌入的对象必须具有正文的邮件。 如果此属性的值为 FALSE，或者如果属性不存在，客户端或服务器必须获得定期 calendar 对象的正文。
  
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

