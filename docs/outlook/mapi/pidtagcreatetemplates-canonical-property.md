---
title: PidTagCreateTemplates 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCreateTemplates
api_type:
- HeaderDef
ms.assetid: d2530009-5de3-4872-a0a5-be1389c4206e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08cf1faa0c3cc4cf61e2253b0026361704fdd0e2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438181"
---
# <a name="pidtagcreatetemplates-canonical-property"></a>PidTagCreateTemplates 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含嵌入的 table 对象, 其中包含对话框模板条目标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CREATE_TEMPLATES  <br/> |
|标识符:  <br/> |0x3604  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>说明

若要了解可以在容器中创建的模板对象, 请对该属性调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法。 生成的对象是一个一次性表, 该表为您可以在容器中创建的所有模板提供条目标识符。 
  
若要创建模板对象, 请从一次性表中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列值调用容器对象的**CreateEntry**方法。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IABContainer::CreateEntry](iabcontainer-createentry.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

