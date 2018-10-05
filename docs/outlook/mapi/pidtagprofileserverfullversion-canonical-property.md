---
title: PidTagProfileServerFullVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8c88a625-da57-3b1d-9887-0a898b722766
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9456178e9426d7a5fe17382d876f507daa0251f4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396174"
---
# <a name="pidtagprofileserverfullversion-canonical-property"></a>PidTagProfileServerFullVersion 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定配置文件中的帐户连接到 Microsoft Exchange Server 完整的版本和内部版本信息。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_SERVER_FULL_VERSION  <br/> |
|标识符：  <br/> |0x663B  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>说明

一个配置文件可以指定一个或多个帐户连接到 Exchange 服务器，但他们必须连接到同一 Exchange 服务器。
  
早于 Microsoft Office Outlook 2007 的 Outlook 版本不支持此属性。 对于那些版本的 Outlook 中，查看配置文件中存在**[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** 。 
  
通常，如果活动邮箱已连接到 Exchange 服务器中，Outlook 2007 **PR_PROFILE_SERVER_FULL_VERSION**属性中的活动配置文件存储完成 Exchange Server 版本信息。 Outlook 中包含的主要和次要版本号和主要和次要版本号**EXCHANGE_STORE_VERSION_NUM**结构存储信息。 例如，若要存储**8.0.685.24**的 Exchange Server 版本标识符的主版本号为 8 和次要版本数字为 0，和主要版本号是 685 和次要版本号为 24。
  
只有一个**PR_PROFILE_SERVER_VERSION**或**PR_PROFILE_SERVER_FULL_VERSION**可能存在于配置文件，但以下任意始终存在配置文件中不能保证。 Outlook 不会写入这两个属性，直到成功连接到 Exchange 服务器。 
  
在 Outlook 对象模型中，您可以使用**NameSpace**对象的**ExchangeMailboxServerVersion**属性查找在其托管主动邮箱的 Exchange Server 的版本。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
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

