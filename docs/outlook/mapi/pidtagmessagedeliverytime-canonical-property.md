---
title: PidTagMessageDeliveryTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageDeliveryTime
api_type:
- HeaderDef
ms.assetid: 4f9d44f2-4faa-4f16-9e33-22f80c17db85
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8ebaea7fb6888e51ee1ef658db53dcf3050644da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325611"
---
# <a name="pidtagmessagedeliverytime-canonical-property"></a>PidTagMessageDeliveryTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件的送达日期和时间。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_DELIVERY_TIME  <br/> |
|标识符:  <br/> |0x0E06  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |邮件时间  <br/> |
   
## <a name="remarks"></a>注解

此属性描述邮件在服务器上的存储时间, 而不是在传输提供程序将邮件从服务器复制到本地存储时的下载时间。
  
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

