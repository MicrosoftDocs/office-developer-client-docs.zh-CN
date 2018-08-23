---
title: PidTagAnr 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAnr
api_type:
- HeaderDef
ms.assetid: eca3d4ff-2e92-4d20-a498-98e0773c1962
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cc5edf1c93ca94fb9d8cab302ccd8e96373cd94
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581942"
---
# <a name="pidtaganr-canonical-property"></a>PidTagAnr 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含在通讯簿容器内容表属性限制中使用的字符串值。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ANR，PR_ANR_A，PR_ANR_W  <br/> |
|标识符：  <br/> |0x360C  <br/> |
|数据类型：  <br/> |PT_UNICODE PT_STRING8  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>注解

这些属性不属于任何对象;它提供通过[SPropertyRestriction](spropertyrestriction.md)结构中的通讯簿提供程序。 此属性包含可以对通讯簿容器内容表，以查找相应邮件的收件人，测试模糊名称解析 (ANR) 字符串。 
  
通讯簿提供程序匹配**PR_ANR**和对在内容表中，每个条目的关联的属性的值使用提供程序定义匹配算法。 此匹配项中使用的列选择算法的一部分提供程序。 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 列中最常用;包含用户的电子邮件名称时，则也可以**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 列。 
  
模糊名称解析的详细信息，请参阅[地址簿限制](address-book-restrictions.md)。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IAddrBook::ResolveName](iaddrbook-resolvename.md)
  
[IABContainer::ResolveNames](iabcontainer-resolvenames.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

