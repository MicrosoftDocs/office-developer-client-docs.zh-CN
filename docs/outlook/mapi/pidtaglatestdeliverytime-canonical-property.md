---
title: PidTagLatestDeliveryTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLatestDeliveryTime
api_type:
- HeaderDef
ms.assetid: 6c2e64bc-786e-4867-a504-46f4d1214337
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3640ec4471b72dea81d56cc2c462ef145095480f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590923"
---
# <a name="pidtaglatestdeliverytime-canonical-property"></a>PidTagLatestDeliveryTime 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的最新的日期和时间时邮件传输代理 (MTA) 应将邮件传递。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_LATEST_DELIVERY_TIME  <br/> |
|标识符:  <br/> |0x0019  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

如果按此属性指定的时间，MTA 无法传送一条消息，它会取消没有传递的邮件。 
  
## <a name="related-resources"></a>相关资源

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

