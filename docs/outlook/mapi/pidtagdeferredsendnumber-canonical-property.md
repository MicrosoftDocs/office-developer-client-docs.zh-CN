---
title: PidTagDeferredSendNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendNumber
api_type:
- HeaderDef
ms.assetid: 8ada5c9b-bec5-42d8-bc58-f0411ec4e88b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 30ee7c1a7eb86fd4cdfe90fb6711bd1b295fd5e6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591084"
---
# <a name="pidtagdeferredsendnumber-canonical-property"></a>PidTagDeferredSendNumber 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含可用于计算延期发送一条消息的数目。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEFERRED_SEND_NUMBER  <br/> |
|标识符：  <br/> |0x3FEB  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

此属性用于计算**PR_DEFERRED_SEND_TIME** ([PidTagDeferredSendTime](pidtagdeferredsendtime-canonical-property.md)) 属性时不存在。 当推迟发送一条消息时， **PR_DEFERRED_SEND_NUMBER**属性应设置以及**PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) 属性中，如果**PR_DEFERRED_SEND_TIME**属性不存在。 
  
**PR_DEFERRED_SEND_NUMBER**值必须介于 0 到 999 之间设置。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
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

