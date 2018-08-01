---
title: PidTagOriginallyIntendedRecipAddrtype 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginallyIntendedRecipAddrtype
api_type:
- COM
ms.assetid: dcfb6bd5-bff5-4a50-aec7-4bdfdabf7631
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ddb2a246ca77f751ddd428941cd16da6aa5e286b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777962"
---
# <a name="pidtagoriginallyintendedrecipaddrtype-canonical-property"></a>PidTagOriginallyIntendedRecipAddrtype 规范属性

  
  
**适用于**： Outlook 
  
包含自动转发邮件的最初预期接收人的地址类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE，PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE_A，PR_ORIGINALLY_INTENDED_RECIP_ADDRTYPE_W  <br/> |
|标识符：  <br/> |0x007B  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |Server  <br/> |
   
## <a name="remarks"></a>说明

这些属性是一个在最初预期的邮件收件人的地址属性。 它必须已转发邮件的自动代理设置。
  
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

