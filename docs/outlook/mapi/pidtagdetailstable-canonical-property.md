---
title: PidTagDetailsTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDetailsTable
api_type:
- HeaderDef
ms.assetid: 7a0ccad3-f497-4871-b733-771e6cb8ef6a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1602d1753d9f7f6e6f407a85dab0a33255db7aae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585785"
---
# <a name="pidtagdetailstable-canonical-property"></a>PidTagDetailsTable 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含嵌入的显示 table 对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DETAILS_TABLE  <br/> |
|标识符：  <br/> |0x3605  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>注解

将此属性传递给对象[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法返回的[IMAPITable](imapitableiunknown.md)接口可用于显示表的创建。 MAPI 使用此表显示通讯簿对象的属性表以响应[IAddrBook::Details](iaddrbook-details.md)呼叫。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[PidTagSearch 规范属性](pidtagsearch-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

