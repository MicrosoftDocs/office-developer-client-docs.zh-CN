---
title: PidLidDistributionListOneOffMembers 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidDistributionListOneOffMembers
api_type:
- COM
ms.assetid: 0b92e654-9e2d-4c2e-9a63-d5fac603b0c0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fed4395274cb790ab8ab7ecf0456d4ecb9ec0134
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335047"
---
# <a name="pidliddistributionlistoneoffmembers-canonical-property"></a>PidLidDistributionListOneOffMembers 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定与个人通讯组列表的成员对应的一次输入 Id 的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidDLOneOffMembers  <br/> |
|属性集：  <br/> |PSETID_Address  <br/> |
|LONG ID (的一) ：  <br/> |0x00008054  <br/> |
|数据类型：  <br/> |PT_MV_BINARY  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

这些一对一 EntryIds 封装个人通讯组列表成员的显示名称和电子邮件地址。
  
如果客户端或服务器设置此属性，则必须与 **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) 属性同步：对于 **dispidDLOneOffMembers** 属性中的每个条目 **，dispidDLMembers** 属性中必须在同一位置有一个条目。 
  
设置 **dispidDLOneOffMembers** 时，客户端或服务器必须确保其总大小小于 15，000 字节的大小。
  
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

