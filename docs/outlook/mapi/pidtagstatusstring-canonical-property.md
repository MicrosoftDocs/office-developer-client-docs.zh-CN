---
title: PidTagStatusString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStatusString
api_type:
- COM
ms.assetid: 42cd946c-c55a-4371-99ee-05e2248fdd5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e8370a613162e3bc8d4395a18e9a7e177255b9b3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567298"
---
# <a name="pidtagstatusstring-canonical-property"></a>PidTagStatusString 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一条消息，指示会话资源的当前状态。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STATUS_STRING，PR_STATUS_STRING_A，PR_STATUS_STRING_W  <br/> |
|标识符：  <br/> |0x3E08  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

这些属性授予服务提供商和 MAPI 能够提供有关状态的会话资源，如集成的通讯簿或特定服务提供商的特定信息。 此属性说明，并提供其他信息的状态代码或**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性。 **PR_STATUS_CODE**是必需的所有状态对象， **PR_STATUS_STRING**和关联的属性是可选的。 传输提供程序不会提供一个值，当 MAPI 后台处理程序提供的默认值。 
  
在与 MAPI 后台处理程序; 远程过程调用的相同端上生成字符串通过共享的内存，而不是跨进程边界被封送传输。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStatusCode 规范属性](pidtagstatuscode-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

