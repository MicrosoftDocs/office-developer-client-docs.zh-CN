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
ms.openlocfilehash: ce08ba971662b7f5060e6b24a6d2c5ee1a921d5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327963"
---
# <a name="pidtaganr-canonical-property"></a>PidTagAnr 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于通讯簿容器内容表的属性限制中的字符串值。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ANR、PR_ANR_A、PR_ANR_W  <br/> |
|标识符:  <br/> |0x360C  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

这些属性不属于任何对象;它由 [SPropertyRestriction](spropertyrestriction.md) 结构中的地址簿提供程序提供。 此属性包含一个不明确的名称解析 (ANR) 字符串，该字符串可以针对通讯簿容器的内容表进行测试以查找相应的邮件收件人。 
  
通讯簿提供程序使用提供程序定义的PR_ANR匹配算法，根据内容表中的每个条目匹配通讯簿和关联属性的值。 提供程序选择此匹配中使用的列作为算法的一部分。 **PidTagDisplay**) Name PR_DISPLAY_NAME ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)列是最常用的列;**PR_ACCOUNT (** [PidTagAccount](pidtagaccount-canonical-property.md)) 列在包含用户的电子邮件名称时也很有用。 
  
有关模糊名称解析详细信息，请参阅 [通讯簿限制](address-book-restrictions.md)。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IAddrBook::ResolveName](iaddrbook-resolvename.md)
  
[IABContainer::ResolveNames](iabcontainer-resolvenames.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

