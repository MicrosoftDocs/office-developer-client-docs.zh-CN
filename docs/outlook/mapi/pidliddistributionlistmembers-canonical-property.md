---
title: PidLidDistributionListMembers 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidDistributionListMembers
api_type:
- COM
ms.assetid: 029767ab-de72-4402-9cc3-31b006591042
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9bfb94b2929f780a428fb932efb3538f94f5aaea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591462"
---
# <a name="pidliddistributionlistmembers-canonical-property"></a>PidLidDistributionListMembers 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定对应的个人通讯组列表成员的对象的 Entryid 的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidDLMembers  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008055  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>注解

个人通讯组列表中的成员可以是其他个人通讯组列表、 联系人、 全局地址列表用户或通讯组列表或一次性电子邮件地址中包含的电子地址。 每个 EntryId 的格式必须是一次性的 EntryId， [[MS-OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)中指定或换行的 EntryId。 
  
设置此属性时，客户端或服务器必须确保其总大小小于 15,000 个字节。
  
此属性指定的一次性 Entryid 对应的个人通讯组列表成员的列表。 这些一次性 Entryid 封装的显示名称和个人通讯组列表成员的电子邮件地址。
  
如果客户端或服务器设置该属性，它必须为每个项的**dispidDLOneOffMembers** ([PidLidDistributionListOneOffMembers](pidliddistributionlistoneoffmembers-canonical-property.md)) 属性中此属性**dispidDLMembers**与同步，必须有中的条目**dispidDLOneOffMembers**中的相同位置。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

