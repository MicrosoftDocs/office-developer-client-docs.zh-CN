---
title: PidTagDeliveryPoint 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeliveryPoint
api_type:
- HeaderDef
ms.assetid: 715a9dbd-78f8-41e1-a76e-29448d06ec19
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e18b08bcbd76cacf7dbb5b5fd36d80d5f266364d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360877"
---
# <a name="pidtagdeliverypoint-canonical-property"></a>PidTagDeliveryPoint 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定功能实体的性质, 方法是通过邮件是由邮件传递的, 还是已传递给收件人。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DELIVERY_POINT  <br/> |
|标识符:  <br/> |0x0C07  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 收件人  <br/> |
   
## <a name="remarks"></a>注解

此属性可以具有下列值之一: 
  
MAPI_MH_DP_ML 
  
> 传递到通讯组列表, 这一传递点又可能将邮件分发给多个收件人。
    
MAPI_MH_DP_MS 
  
> 传递到邮件存储, 而不是直接传递给收件人。
    
MAPI_MH_DP_OTHER_AU 
  
> 传递给除物理传递访问单元 (PDAU) 以外的访问单元 (AU), 例如传真系统。
    
MAPI_MH_DP_PDAU 
  
> 传递给物理传递访问单元, 如 "人体邮政" 运营商。
    
MAPI_MH_DP_PDS_PATRON 
  
> 传递到物理传递系统 patron, 如常规邮政邮箱。
    
MAPI_MH_DP_PRIVATE_UA 
  
> 传递给私有用户代理 (UA), 例如内部邮件系统中的客户端。
    
MAPI_MH_DP_PUBLIC_UA 
  
> 传递给公用用户代理或公共服务提供商。
    
默认值为 MAPI_MH_DP_PRIVATE_UA, 即 MAPI 客户端。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

