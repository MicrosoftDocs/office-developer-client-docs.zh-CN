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
ms.openlocfilehash: 74eae4a4ed742c3bb90496f5975ad7dac6ff798f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419252"
---
# <a name="pidtagdetailstable-canonical-property"></a>PidTagDetailsTable 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含嵌入的显示表对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DETAILS_TABLE  <br/> |
|标识符:  <br/> |0x3605  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>说明

将此属性传递给对象的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法将返回允许创建显示表的[IMAPITable](imapitableiunknown.md)接口。 MAPI 使用此表显示通讯簿对象的属性表以响应[IAddrBook::D etails](iaddrbook-details.md)调用。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[PidTagSearch 规范属性](pidtagsearch-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

