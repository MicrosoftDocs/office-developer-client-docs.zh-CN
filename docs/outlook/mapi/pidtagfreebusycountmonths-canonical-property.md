---
title: PidTagFreeBusyCountMonths 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyCountMonths
api_type:
- HeaderDef
ms.assetid: 278a77f2-65ec-4281-b406-942cc416a476
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5ba76b5735687e3bb65e530b3de0d257754559c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777666"
---
# <a name="pidtagfreebusycountmonths-canonical-property"></a>PidTagFreeBusyCountMonths 规范属性

  
  
**适用于**： Outlook 
  
包含用于计算将其发布到公用文件夹的忙/闲数据范围的开始和结束日期值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FREEBUSY_COUNT_MONTHS  <br/> |
|标识符：  <br/> |0x6869  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |类定义消息可传送  <br/> |
   
## <a name="remarks"></a>说明

此属性的值必须大于或等于 0 且小于或等于 36。 这不是必需的属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> 发布的用户或资源的可用性。
    
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
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

