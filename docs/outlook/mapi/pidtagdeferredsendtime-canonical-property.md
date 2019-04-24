---
title: PidTagDeferredSendTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendTime
api_type:
- HeaderDef
ms.assetid: ee206c2d-8371-4d19-b42b-78f6479e13ca
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d6374c2fd3c277e2bb976930e9e105cc839b1e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359876"
---
# <a name="pidtagdeferredsendtime-canonical-property"></a>PidTagDeferredSendTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示客户端希望延迟发送邮件的时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEFERRED_SEND_TIME  <br/> |
|标识符:  <br/> |0x3FEF  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

如果**PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) 和**PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) 属性存在, 则使用下面的公式重新计算此属性的值, 并旧值将被忽略。
  
 **PR_DEFERRED_SEND_TIME** = **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) + **PR_DEFERRED_SEND_NUMBER** * TimeOf (**PR_DEFERRED_SEND_UNITS**)
  
如果**PR_DEFERRED_SEND_TIME**值早于当前时间 (以 UTC 为单位), 则会立即发送邮件。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

