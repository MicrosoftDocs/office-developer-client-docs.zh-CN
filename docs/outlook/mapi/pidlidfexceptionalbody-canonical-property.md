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
ms.openlocfilehash: 93eb98aee19ea3f46a4e01e2c80150c3efe893a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327459"
---
# <a name="pidlidfexceptionalbody-canonical-property"></a>PidLidFExceptionalBody 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示异常嵌入邮件对象具有与定期日历对象不同的正文。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFExceptionalBody  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x00008206  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

如果此属性的值为 TRUE, 则异常嵌入邮件对象必须具有正文。 如果此属性的值为 FALSE, 或者属性不存在, 则客户端或服务器必须从定期日历对象中获取正文。
  
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

