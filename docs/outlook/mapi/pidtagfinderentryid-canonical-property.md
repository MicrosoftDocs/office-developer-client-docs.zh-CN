---
title: PidTagFinderEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFinderEntryId
api_type:
- HeaderDef
ms.assetid: a3895f90-7561-4b41-92af-ecc8614e4211
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2ec8b776bddc21d356d6e803f56f6f26738a9747
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590741"
---
# <a name="pidtagfinderentryid-canonical-property"></a>PidTagFinderEntryId 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含通常创建搜索结果的文件夹的项标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FINDER_ENTRYID  <br/> |
|标识符：  <br/> |0x35E7  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>注解

此属性中包含的项标识符具有相同的格式为[ENTRYID](entryid.md)结构。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

