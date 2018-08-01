---
title: PidTagResourceType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourceType
api_type:
- COM
ms.assetid: 48b634d7-deea-422b-8944-a8d929d83838
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d494577721feba01dd9cb93f344308251a8ed33
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778248"
---
# <a name="pidtagresourcetype-canonical-property"></a>PidTagResourceType 规范属性

  
  
**适用于**： Outlook 
  
包含一个值，指示的服务提供程序类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_TYPE  <br/> |
|标识符：  <br/> |0x3E03  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>说明

此属性可以具有完全下列值之一：
  
MAPI_AB 
  
> 通讯簿
    
MAPI_AB_PROVIDER 
  
> 通讯簿提供程序
    
MAPI_HOOK_PROVIDER 
  
> 后台处理程序挂接提供程序
    
MAPI_PROFILE_PROVIDER 
  
> 配置文件提供程序
    
MAPI_SPOOLER 
  
> 消息后台处理程序
    
MAPI_STORE_PROVIDER 
  
> 消息存储提供程序
    
MAPI_SUBSYSTEM 
  
> 内部 MAPI 子系统
    
MAPI_TRANSPORT_PROVIDER 
  
> 传输提供程序
    
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

