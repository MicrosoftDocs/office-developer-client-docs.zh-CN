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
  
指定与个人通讯组列表的成员对应的对象的 EntryIds 列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidDLMembers  <br/> |
|属性集：  <br/> |PSETID_Address  <br/> |
|LONG ID (的一) ：  <br/> |0x00008055  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

个人通讯组列表的成员可以是其他个人通讯组列表、联系人中包含的电子地址、全局地址列表用户或通讯组列表，或者是一次电子邮件地址。 每个 EntryId 的格式必须是 [[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx) 中指定的一次 EntryId 或包装的 EntryId。 
  
设置此属性时，客户端或服务器必须确保其总大小小于 15，000 字节。
  
此属性指定与个人通讯组列表的成员对应的一次 EntryId 的列表。 这些一对一 EntryIds 封装个人通讯组列表成员的显示名称和电子邮件地址。
  
如果客户端或服务器设置此属性，则它必须与 **dispidDLOneOffMembers** ([PidLidDistributionListOneOffMembers](pidliddistributionlistoneoffmembers-canonical-property.md)) 属性中每个条目的此属性 **dispidDLMembers** 同步 **，dispidDLOneOffMembers** 中必须在同一位置有一个条目。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

