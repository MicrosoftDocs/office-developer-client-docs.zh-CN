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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327445"
---
# <a name="pidtagrpcoverhttpflags-canonical-property"></a>PidTagRpcOverHttpFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含由 Microsoft Office Outlook 用于通过超文本传输协议 (HTTP) 使用远程过程调用 (RPC) 连接到 microsoft Exchange Server 的配置文件中的设置。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ROH_FLAGS  <br/> |
|标识符:  <br/> |0x6623  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>注解

**PR_ROH_FLAGS**属性存储在邮件应用程序编程接口 (MAPI) 配置文件的 "全局配置文件" 部分中。 **PR_ROH_FLAGS**的值是由一个或多个下列标志组成的位掩码。 
  
|**Name**|**Value**|**说明**|
|:-----|:-----|:-----|
|**ROHFLAGS_USE_ROH** <br/> |0x1  <br/> |使用 RPC over HTTP 连接到 Exchange 服务器。  <br/> |
|**ROHFLAGS_SSL_ONLY** <br/> |0x2  <br/> |仅使用安全套接字层 (SSL) 连接到 Exchange 服务器。  <br/> |
|**ROHFLAGS_MUTUAL_AUTH** <br/> |0x4  <br/> |使用 SSL 连接时相互验证会话。  <br/> |
|**ROHFLAGS_HTTP_FIRST_ON_FAST** <br/> |0x8  <br/> |在快速网络中, 先使用 HTTP 进行连接。 然后, 使用 tcp/ip 进行连接。  <br/> |
|**ROHFLAGS_HTTP_FIRST_ON_SLOW** <br/> |0x20  <br/> |在低速网络中, 先使用 HTTP 进行连接。 然后, 使用 tcp/ip 进行连接。  <br/> |
   
例如, 若要将**PR_ROH_FLAGS**属性设置为启用 RPC over HTTP, 需要 SSL, 并指定应首先在低速连接上使用 HTTP 协议, 请将**PR_ROH_FLAGS**属性`ROHFLAGS_USE_ROH | ROHFLAGS_SSL_ONLY | ROHFLAGS_HTTP_FIRST_ON_SLOW`的值设置为等于0x23 的值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义在远程操作中使用的基本数据结构。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

