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
ms.openlocfilehash: 098261cd71631e4816d22272e1b1bef1d5932a94
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540943"
---
# <a name="pidnameexchangejunkemailmovestamp-canonical-property"></a>PidNameExchangeJunkEmailMoveStamp 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含持久性的邮件值，该值指示邮件不应由垃圾邮件筛选器处理，因为该邮件已处理或是安全的。
  
|||
|:-----|:-----|
|友好名称：  <br/> |无  <br/> |
|属性集：  <br/> |PS_PUBLIC_STRINGS  <br/> |
|属性名称：  <br/> |http://schemas.microsoft.com/exchange/junkemailmovestamp  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |安全消息传递  <br/> |
   
## <a name="remarks"></a>备注

此属性标记在由垃圾邮件规则移动的每封邮件上，或作为其他方式受信任的内容。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许/阻止列表的处理和垃圾邮件的确定。
    
[[MS-OXORSS]](https://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)
  
> 指定表示 RSS 项目的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

