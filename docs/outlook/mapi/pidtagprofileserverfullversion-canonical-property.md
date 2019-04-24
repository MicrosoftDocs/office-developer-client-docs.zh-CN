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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341599"
---
# <a name="pidtagprofileserverfullversion-canonical-property"></a>PidTagProfileServerFullVersion 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定与配置文件中的帐户连接的 Microsoft Exchange Server 的完整版本和内部版本信息。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_SERVER_FULL_VERSION  <br/> |
|标识符:  <br/> |0x663B  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>注解

配置文件可以指定连接到 exchange 服务器的一个或多个帐户, 但这些帐户必须连接到同一个 exchange 服务器。
  
早于 Microsoft Office Outlook 2007 版本的 Outlook 不支持该属性。 对于这些版本的 Outlook, 请检查配置文件中是否存在**[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** 。 
  
通常情况下, 如果活动邮箱连接到 Exchange 服务器, Outlook 2007 将在活动配置文件中的**PR_PROFILE_SERVER_FULL_VERSION**属性中存储完整的 Exchange Server 版本信息。 Outlook 将信息存储在**EXCHANGE_STORE_VERSION_NUM**结构中, 其中包含主版本号和次版本号以及主要和次要内部版本号。 例如, 若要存储**8.0.685.24**的 Exchange Server 版本标识符, 主要版本号为 8, 次要版本号为 0, 主内部版本号为 685, 次要内部版本号为24。
  
只有**PR_PROFILE_SERVER_VERSION**或 PR_PROFILE_SERVER_FULL_VERSION 中的一个可能存在于配置文件中, 但不能保证在配置文件中始终存在这两个**** 。 Outlook 在成功连接到 Exchange 服务器之前, 不会写入其中的任何一个属性。 
  
在 Outlook 对象模型中, 可以使用**NameSpace**对象的**ExchangeMailboxServerVersion**属性来查找托管活动邮箱的 Exchange 服务器的版本。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
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

