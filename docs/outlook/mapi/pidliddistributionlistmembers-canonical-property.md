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
ms.openlocfilehash: f04d1593e2a13a2bfc23412340d7eb9f38f5d9ef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335068"
---
# <a name="pidliddistributionlistmembers-canonical-property"></a>PidLidDistributionListMembers 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定与个人通讯组列表的成员相对应的对象的 entryid 列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidDLMembers  <br/> |
|属性集:  <br/> |PSETID_Address  <br/> |
|长 ID (盖子):  <br/> |0x00008055  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |Contact  <br/> |
   
## <a name="remarks"></a>注解

个人通讯组列表的成员可以是其他个人通讯组列表、联系人中包含的电子地址、全局地址列表用户或通讯组列表或一次性电子邮件地址。 每个 EntryId 的格式必须是一个一次性的 entryid, 在[[OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)或已包装的 entryid 中指定。 
  
设置此属性时, 客户端或服务器必须确保其总大小小于15000字节。
  
此属性指定与个人通讯组列表的成员相对应的一次性 entryid 的列表。 这些一次性 entryid 封装个人通讯组列表成员的显示名称和电子邮件地址。
  
如果客户端或服务器设置此属性, 则必须将其与**dispidDLOneOffMembers** ([PidLidDistributionListOneOffMembers](pidliddistributionlistoneoffmembers-canonical-property.md)) 属性中的每个条目的**dispidDLMembers**属性同步。在**dispidDLOneOffMembers**中的位置相同。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

