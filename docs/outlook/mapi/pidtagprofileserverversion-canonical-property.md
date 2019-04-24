---
title: PidTagProfileServerVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5d41a536-81ff-733c-2fd7-460798e057c8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 84ff229e9914ec9074d61023873279b110fb606a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286564"
---
# <a name="pidtagprofileserverversion-canonical-property"></a>PidTagProfileServerVersion 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定与 microsoft Outlook 配置文件中的帐户连接的 microsoft Exchange Server 版本的相关信息。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_SERVER_VERSION  <br/> |
|标识符:  <br/> |0x661B  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>注解

配置文件可以指定连接到 exchange 服务器的一个或多个帐户, 但这些帐户必须连接到同一个 exchange 服务器。
  
早于 Microsoft Office outlook 2007 的 outlook 版本可以写入此属性, 以存储与活动配置文件连接的 Exchange 服务器版本相关信息。 但是, 版本信息的格式因不同版本的 Exchange Server 而异。 例如, Outlook 在**PR_PROFILE_SERVER_VERSION**中存储十进制值 6944, 以仅表示 Microsoft Exchange SERVER 2003 的**6.5.6944.3**版本标识符中的主要内部版本号。 对于 Exchange 2007 连接, Outlook 将主版本号和主要内部版本号存储在属性中这些数字的连接的十六进制表示形式中。 **8.0.685.24**的 Exchange 2007 版本标识符的主要版本号为 8, 主要版本号为685的十进制数。 将这两个数字都转换为十六进制, 可以获取0x8 和0x2AD。 Outlook 将这两个数字串联在**PR_PROFILE_SERVER_VERSION**中以十六进制表示形式存储值0x82AD。 
  
Outlook 2007 不会读取或写入该属性。 它支持**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**。 
  
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

