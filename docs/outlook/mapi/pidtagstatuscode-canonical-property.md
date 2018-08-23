---
title: PidTagStatusCode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStatusCode
api_type:
- COM
ms.assetid: e29190c5-52c3-4ef7-98db-699487c54325
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a60bc55686e883cabd144af3a9badfb55f835472
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593121"
---
# <a name="pidtagstatuscode-canonical-property"></a>PidTagStatusCode 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含这些标志指示会话资源的当前状态的位掩码。 所有服务提供商都设置状态代码一样 MAPI 子系统、 MAPI 后台处理程序和集成的通讯簿的状态报告。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STATUS_CODE  <br/> |
|标识符：  <br/> |0x3E04  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

状态代码必须 Mapisvc.inf 文件中出现的所有提供商。 
  
通过 MAPI 和所有服务提供商实现状态对象。 有两组状态代码、 的所有状态对象的一组和传输提供程序的另一组有效的值。 所有状态对象可以将此属性都设置为下列值：
  
STATUS_AVAILABLE 
  
> 指示资源正常工作。
    
STATUS_FAILURE 
  
> 指示资源遇到问题。 服务提供程序 STATUS_FAILURE 指示提供程序可能很快将关闭结束当前会话。
    
STATUS_OFFLINE 
  
> 指示仅本地数据或服务都是可用。
    
传输提供程序还可以设置其状态对象的**PR_STATUS_CODE**属性为下列值： 
  
STATUS_INBOUND_ACTIVE 
  
> 指示的传输提供程序接收的入站的邮件。 
    
STATUS_INBOUND_ENABLED 
  
> 指示的传输提供程序可接受入站的邮件。
    
STATUS_INBOUND_FLUSH 
  
> 指示的传输提供程序从入站队列中下载邮件。
    
STATUS_OUTBOUND_ACTIVE 
  
> 指示的传输提供程序接收出站邮件。 
    
STATUS_OUTBOUND_ENABLED 
  
> 指示的传输提供程序可以处理出站邮件。
    
STATUS_OUTBOUND_FLUSH 
  
> 指示的传输提供程序为上载从其出站队列的消息。
    
STATUS_REMOTE_ACCESS 
  
> 指示的传输提供程序支持远程访问。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStatusString 规范属性](pidtagstatusstring-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

