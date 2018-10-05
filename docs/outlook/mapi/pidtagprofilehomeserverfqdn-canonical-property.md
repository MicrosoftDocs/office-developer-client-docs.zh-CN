---
title: PidTagProfileHomeServerFQDN 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 80273b50-bc16-4be2-8471-1a127b6786bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aef4a932da35f3c4955bc2f4b265b146775c6d87
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400353"
---
# <a name="pidtagprofilehomeserverfqdn-canonical-property"></a>PidTagProfileHomeServerFQDN 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启用 Kerberos 身份验证的配置文件配置。
  
****

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_HOME_SERVER_FQDN  <br/> |
|标识符：  <br/> |0x662A001F  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>说明

此属性设置为用户的目录服务器的域名允许直接连接到域控制器 (DC)，它是已配置为使用针对 Microsoft Exchange Server 2007 的 Kerberos 身份验证的配置文件和早期版本中，通过在**PR_PROFILE_AUTH_PACKAGE**中设置**RPC_C_AUTHN_GSS_KERBEROS** 。
  
> [!NOTE]
> Microsoft Exchange Server 2010 和 Exchange Server 2013 处理从 Exchange Server 2007 和早期版本进行处理的方式不同对客户端访问服务器的地址簿呼叫。 不再使用 DSProxy 过程，因此 Kerberos 身份验证可能失败。 但是，客户端仍都将与 Exchange 服务器而不是直接与 DC，可能不需要通信： 设置**PR_PROFILE_HOME_SERVER_FQDN**避免这。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)
  
> 指定允许的操作的核心消息存储对象。
    
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

