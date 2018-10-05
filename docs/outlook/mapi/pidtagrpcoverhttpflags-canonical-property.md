---
title: PidTagRpcOverHttpFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c8b30768-cf83-450d-9fe2-567a5e0c2f57
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cf1f3b4d72426fb5f80decdc074a622b140657c8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388264"
---
# <a name="pidtagrpcoverhttpflags-canonical-property"></a>PidTagRpcOverHttpFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 Microsoft Office Outlook 用于使用远程过程调用 (RPC) 通过超文本传输协议 (HTTP) 连接到 Microsoft Exchange Server 配置文件中的设置。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ROH_FLAGS  <br/> |
|标识符：  <br/> |0x6623  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>说明

**PR_ROH_FLAGS**属性存储在邮件应用程序编程接口 (MAPI) 配置文件的全局配置文件部分中。 **PR_ROH_FLAGS**的值是一个位掩码，一个或多个以下标志组成。 
  
|**名称**|**值**|**说明**|
|:-----|:-----|:-----|
|**ROHFLAGS_USE_ROH** <br/> |0x1  <br/> |连接到 Exchange 服务器使用 RPC over HTTP。  <br/> |
|**ROHFLAGS_SSL_ONLY** <br/> |0x2  <br/> |连接到 Exchange 服务器仅使用安全套接字层 (SSL)。  <br/> |
|**ROHFLAGS_MUTUAL_AUTH** <br/> |0x4  <br/> |相互验证会话时通过使用 SSL 连接。  <br/> |
|**ROHFLAGS_HTTP_FIRST_ON_FAST** <br/> |0x8  <br/> |在快速网络中，通过先使用 HTTP 连接。 然后，通过使用 tcp/ip 进行连接。  <br/> |
|**ROHFLAGS_HTTP_FIRST_ON_SLOW** <br/> |0x20  <br/> |在慢速网络上通过先使用 HTTP 连接。 然后，通过使用 tcp/ip 进行连接。  <br/> |
   
例如，若要设置**PR_ROH_FLAGS**打开 RPC over HTTP，需要 SSL，并指定应低速连接时，首先使用 HTTP 协议的属性设置为**PR_ROH_FLAGS**属性的值`ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW`即等于 0x23。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
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

