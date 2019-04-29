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
ms.openlocfilehash: 751be8abe02dfb1d5bab2bcbbbc0cbd2a8243f85
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418512"
---
# <a name="pidtagstatuscode-canonical-property"></a>PidTagStatusCode 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指示会话资源的当前状态的标志的位掩码。 所有服务提供程序都会将状态代码设置为 mapi, 以报告子系统的状态、MAPI 后台处理程序和集成的通讯簿。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STATUS_CODE  <br/> |
|标识符:  <br/> |0x3E04  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>说明

状态代码必须出现在所有提供程序的 mapisvc.inf 文件中。 
  
Status 对象由 MAPI 和所有服务提供商实现。 状态代码有两组有效值, 一组用于所有状态对象, 另一组用于传输提供程序。 所有 status 对象均可将此属性设置为以下值:
  
STATUS_AVAILABLE 
  
> 指示资源是可操作的。
    
STATUS_FAILURE 
  
> 指示资源遇到问题。 对于服务提供程序, STATUS_FAILURE 指示可能很快会关闭提供程序以结束当前会话。
    
STATUS_OFFLINE 
  
> 指示仅本地数据或服务可用。
    
传输提供程序还可以将其 status 对象的**PR_STATUS_CODE**属性设置为以下值: 
  
STATUS_INBOUND_ACTIVE 
  
> 指示传输提供程序正在接收入站邮件。 
    
STATUS_INBOUND_ENABLED 
  
> 指示传输提供程序可以接收入站邮件。
    
STATUS_INBOUND_FLUSH 
  
> 指示传输提供程序正在从入站队列下载邮件。
    
STATUS_OUTBOUND_ACTIVE 
  
> 指示传输提供程序正在接收出站邮件。 
    
STATUS_OUTBOUND_ENABLED 
  
> 指示传输提供程序可以处理出站邮件。
    
STATUS_OUTBOUND_FLUSH 
  
> 指示传输提供程序正在从其出站队列中上载邮件。
    
STATUS_REMOTE_ACCESS 
  
> 指示传输提供程序支持远程访问。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStatusString 规范属性](pidtagstatusstring-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

