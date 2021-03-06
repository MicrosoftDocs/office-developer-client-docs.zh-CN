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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341592"
---
# <a name="pidtagprofilehomeserverfqdn-canonical-property"></a>PidTagProfileHomeServerFQDN 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启用配置文件配置的 Kerberos 身份验证。
  
****

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_HOME_SERVER_FQDN  <br/> |
|标识符:  <br/> |0x662A001F  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>备注

将此属性设置为用户目录服务器的域名允许直接连接到域控制器 (DC) ，对于已配置为针对 Microsoft Exchange Server 2007 和早期版本使用 Kerberos 身份验证的配置文件来说，此连接是必需的，方法为在 **PR_PROFILE_AUTH_PACKAGE** 中设置 **RPC_C_AUTHN_GSS_KERBEROS。**
  
> [!NOTE]
> Microsoft Exchange Server 2010 和 Exchange Server 2013 处理对客户端访问服务器的通讯簿调用的方式与 Exchange Server 2007 和早期版本处理这些呼叫的方式不同。 不再使用 DSProxy 进程，因此 Kerberos 身份验证可能会成功。 但是，客户端仍将与 Exchange 服务器通信，而不是直接与 DC 通信，这可能不需要：设置 **PR_PROFILE_HOME_SERVER_FQDN可以避免这种情况**。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)
  
> 指定核心邮件存储对象的允许操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

