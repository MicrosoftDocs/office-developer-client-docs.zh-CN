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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397637"
---
# <a name="pidtagprofileserverversion-canonical-property"></a>PidTagProfileServerVersion 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定的 Microsoft Outlook 配置文件中的帐户连接到 Microsoft Exchange Server 版本信息。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_SERVER_VERSION  <br/> |
|标识符：  <br/> |0x661B  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>说明

一个配置文件可以指定一个或多个帐户连接到 Exchange 服务器，但他们必须连接到同一 Exchange 服务器。
  
早于 Microsoft Office Outlook 2007 的 Outlook 版本可以写入此属性存储的活动配置文件连接到 Exchange Server 版本信息。 但是，版本信息的格式不同的不同版本的 Exchange Server。 例如， **PR_PROFILE_SERVER_VERSION** 6944 的十进制值表示仅主要中的 Outlook 存储区中的版本标识符的版本号**6.5.6944.3** Microsoft Exchange Server 2003。 对于 Exchange 2007 连接，Outlook 存储的主版本号和主版本号的串联十六进制表示的属性中的这些号码。 Exchange 2007 版本的**8.0.685.24**标识符具有十进制主版本号 8 和主要版本号 685。 您将这两个数字转换为十六进制数，获取 0x8 和 0x2AD。 将这两个数字，Outlook 将值存储 0x82AD **PR_PROFILE_SERVER_VERSION**十六进制表示中。 
  
Outlook 2007 不读取或写入到此属性。 它支持**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**。 
  
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

