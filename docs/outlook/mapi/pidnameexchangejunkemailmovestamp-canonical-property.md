---
title: PidNameExchangeJunkEmailMoveStamp 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameExchangeJunkEmailMoveStamp
api_type:
- COM
ms.assetid: 7a52f46c-371c-46d0-8d66-e154482e8269
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1312f590dfc0e8388495351dd4870fcf8b9e22f0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591364"
---
# <a name="pidnameexchangejunkemailmovestamp-canonical-property"></a>PidNameExchangeJunkEmailMoveStamp 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含持久化的消息值，该值指示的消息因为已处理或安全，邮件不应处理垃圾邮件筛选器。
  
|||
|:-----|:-----|
|友好名称：  <br/> |无  <br/> |
|属性进行设置：  <br/> |PS_PUBLIC_STRINGS  <br/> |
|属性名称：  <br/> |http://schemas.microsoft.com/exchange/junkemailmovestamp  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |安全邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性标记上每封邮件的垃圾邮件规则移动或否则受信任的内容。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许处理的允许/阻止列表，并确定的垃圾邮件。
    
[[MS OXORSS]](http://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)
  
> 指定的属性和表示 RSS 项目的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

