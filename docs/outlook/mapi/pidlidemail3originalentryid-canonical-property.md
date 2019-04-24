---
title: PidLidEmail3OriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3OriginalEntryId
api_type:
- COM
ms.assetid: b290d4a4-8d70-4656-9254-191c5179662f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fd8e600f0acb16d23690fc16245988a53e22c7c8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338008"
---
# <a name="pidlidemail3originalentryid-canonical-property"></a>PidLidEmail3OriginalEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定与第三个电子邮件地址对应的对象的**EntryId** 。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidEmail3OriginalEntryID  <br/> |
|属性集:  <br/> |PSETID_Address  <br/> |
|长 ID (盖子):  <br/> |0x000080A5  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Contact  <br/> |
   
## <a name="remarks"></a>注解

此属性的值必须是此电子地址的一次性**条目**id 或有效的通讯簿对象**EntryId**。
  
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

