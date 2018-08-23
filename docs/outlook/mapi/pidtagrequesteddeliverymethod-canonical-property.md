---
title: PidTagRequestedDeliveryMethod 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRequestedDeliveryMethod
api_type:
- COM
ms.assetid: cc55089b-e389-405e-8174-f5b5ec352f78
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f18d726c1b06a6fb7f79964165bbdb9074a6d4d7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571365"
---
# <a name="pidtagrequesteddeliverymethod-canonical-property"></a>PidTagRequestedDeliveryMethod 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
此属性包含邮件发件人的发挥二进制交付方法 （服务提供商） 的数组。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REQUESTED_DELIVERY_METHOD  <br/> |
|标识符：  <br/> |0x0C18  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 收件人  <br/> |
   
## <a name="remarks"></a>注解

数组包含在此属性为每个服务提供商包含 ASN.1 标识符。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

