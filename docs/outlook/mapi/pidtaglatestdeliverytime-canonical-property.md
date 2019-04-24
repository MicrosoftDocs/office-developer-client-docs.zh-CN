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
ms.openlocfilehash: 77ca51ae5a0e7e1d5a9be8f4ca05a1187fe71694
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279850"
---
# <a name="pidtaglatestdeliverytime-canonical-property"></a>PidTagLatestDeliveryTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件传输代理 (MTA) 应在何时传递邮件的最新日期和时间。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_LATEST_DELIVERY_TIME  <br/> |
|标识符:  <br/> |0x0019  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

如果 MTA 无法通过此属性指定的时间传递邮件, 它将取消邮件而不进行传递。 
  
## <a name="related-resources"></a>相关资源

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

