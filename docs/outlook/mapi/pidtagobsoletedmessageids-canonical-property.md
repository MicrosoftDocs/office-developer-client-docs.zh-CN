---
title: PidTagObsoletedMessageIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagObsoletedMessageIds
api_type:
- HeaderDef
ms.assetid: bc979398-f1ad-4496-b982-428b95719369
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1717e30679fb3f6721690db75fb5dd402048eb09
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575047"
---
# <a name="pidtagobsoletedmessageids-canonical-property"></a>PidTagObsoletedMessageIds 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含此消息取代的消息的标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_OBSOLETED_IPMS  <br/> |
|标识符：  <br/> |0x001F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Server  <br/> |
   
## <a name="remarks"></a>注解

此属性中包含的标识符是标准搜索键使用**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性的格式。
  
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

