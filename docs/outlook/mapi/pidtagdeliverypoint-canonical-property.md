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
ms.openlocfilehash: 803481a71d505fc9f12e77b162a91200cac505d6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777556"
---
# <a name="pidtagdeliverypoint-canonical-property"></a>PidTagDeliveryPoint 规范属性

  
  
**适用于**： Outlook 
  
指定一条消息已通过其或已传递给收件人功能实体的特性。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DELIVERY_POINT  <br/> |
|标识符：  <br/> |0x0C07  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 收件人  <br/> |
   
## <a name="remarks"></a>说明

此属性可以具有完全下列值之一： 
  
MAPI_MH_DP_ML 
  
> 传递给通讯组列表，收信人地址的反过来可能分发很多个收件人的邮件。
    
MAPI_MH_DP_MS 
  
> 传递给而不是直接向收件人的消息存储。
    
MAPI_MH_DP_OTHER_AU 
  
> 物理传递访问单位 (PDAU)，如传真系统之外送达访问单元 (AU)。
    
MAPI_MH_DP_PDAU 
  
> 发送到物理传递访问单位，如 human 邮政运营商。
    
MAPI_MH_DP_PDS_PATRON 
  
> 发送到物理传递系统记录，如传统的邮政邮箱。
    
MAPI_MH_DP_PRIVATE_UA 
  
> 例如，内部邮件系统中的客户端送达专用用户代理 (UA)。
    
MAPI_MH_DP_PUBLIC_UA 
  
> 传递到公共用户代理或公共服务提供商。
    
默认值是 MAPI_MH_DP_PRIVATE_UA，即，MAPI 客户端。 
  
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

