---
title: PidTagRecipientProposed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientProposed
api_type:
- COM
ms.assetid: 8cb0e46c-0937-482f-be78-1f2e5261b210
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3b05f33328e9e0b90251a99defa9816f86971337
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778152"
---
# <a name="pidtagrecipientproposed-canonical-property"></a>PidTagRecipientProposed 规范属性

  
  
**适用于**： Outlook 
  
指示是否已经响应会议与会者。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RECIPIENT_PROPOSED  <br/> |
|标识符:  <br/> |0x5FE1  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |传输收件人  <br/> |
   
## <a name="remarks"></a>备注

值为 TRUE 的此属性表示与会者提出建议新的日期和/或时间。 值为 FALSE 或不存在此属性是指与会者不具有尚未响应，或从参与者的最新响应未不包括新的日期 / 时间建议。 该值必须在 TRUE 不是定期系列中的与会者。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

