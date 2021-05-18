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
  
指定有关 Microsoft Microsoft Exchange Server配置文件中帐户Outlook版本的信息。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROFILE_SERVER_VERSION  <br/> |
|标识符:  <br/> |0x661B  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 配置文件配置  <br/> |
   
## <a name="remarks"></a>备注

配置文件可以指定一个或多个连接到Exchange Server帐户，但它们必须连接到同一Exchange Server。
  
2007 Outlook 2007 Microsoft Office Outlook版本可以写入此属性以存储有关活动配置文件Exchange Server的版本的有关的信息。 但是，版本信息的格式因版本不同而异Exchange Server。 例如，Outlook在 **PR_PROFILE_SERVER_VERSION** 中存储小数值 6944，以仅表示 Microsoft Exchange Server 2003 版本标识符 **6.5.6944.3** 的主要内部版本号。 对于 Exchange 2007 连接，Outlook 将主版本号和主内部版本号存储在 属性中这些编号的串联十六进制表示形式中。 **8.0.685.24 Exchange 2007** 版本标识符的主要版本号为 8，主要内部版本号为 685（十进制）。 将两个数字转换为十六进制，0x8和0x2AD。 连接这两个数字Outlook，以十六0x82AD十六PR_PROFILE_SERVER_VERSION形式存储值。  
  
Outlook 2007 不读取或写入此属性。 它支持 **[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**。 
  
配置文件中 **PR_PROFILE_SERVER_VERSION** 或PR_PROFILE_SERVER_FULL_VERSION中的一个，但无法保证配置文件中始终存在其中一个。 Outlook在成功连接到任一属性之前，不会向该属性Exchange Server。 
  
在Outlook模型中，可以使用 **NameSpace** 对象的 **ExchangeMailboxServerVersion** 属性查找托管活动邮箱的 Exchange Server 版本。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
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

