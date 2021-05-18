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
ms.openlocfilehash: 9b4510a32fe14e4316a6bcddafcc163ee899436e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421562"
---
# <a name="pidtagstatusstring-canonical-property"></a>PidTagStatusString 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一条消息，指示会话资源的当前状态。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STATUS_STRING、PR_STATUS_STRING_A、PR_STATUS_STRING_W  <br/> |
|标识符:  <br/> |0x3E08  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

这些属性使服务提供商和 MAPI 有机会提供有关会话资源状态的特定信息，例如集成通讯簿或特定服务提供商。 此属性解释并提供有关[PidTagStatusCode](pidtagstatuscode-canonical-property.md) PR_STATUS_CODE (状态代码) 信息。 尽管 **PR_STATUS_CODE** 状态对象都需要此参数，PR_STATUS_STRING属性和关联属性是可选的。 当传输提供程序未提供值时，MAPI 后台处理程序会提供默认值。 
  
该字符串在远程过程调用的同一端与 MAPI 后台处理程序一起生成;它通过共享内存，而不是跨进程边界封送。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStatusCode 规范属性](pidtagstatuscode-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

