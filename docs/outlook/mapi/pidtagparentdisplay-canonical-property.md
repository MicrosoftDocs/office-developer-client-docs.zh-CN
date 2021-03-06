---
title: PidTagParentDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagParentDisplay
api_type:
- COM
ms.assetid: 6a36f4fb-17c0-4271-87d4-a92895f35f23
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7aef4c1d83672033662502ad0950b7bac9f58c52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429500"
---
# <a name="pidtagparentdisplay-canonical-property"></a>PidTagParentDisplay 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含显示名称中发现邮件的文件夹的行数。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PARENT_DISPLAY、PR_PARENT_DISPLAY_A、PR_PARENT_DISPLAY_W  <br/> |
|标识符:  <br/> |0x0E05  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 不可传输  <br/> |
   
## <a name="remarks"></a>备注

这些属性不在任何对象上。 它们只能出现在搜索结果文件夹的内容表中。
  
这些属性和 **PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性之间不相关。 它们属于完全不同的上下文。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

