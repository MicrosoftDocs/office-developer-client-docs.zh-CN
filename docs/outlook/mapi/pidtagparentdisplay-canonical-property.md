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
ms.openlocfilehash: ce9fea80a2dfed25002e5500dd4defaf5ff04421
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778030"
---
# <a name="pidtagparentdisplay-canonical-property"></a>PidTagParentDisplay 规范属性

  
  
**适用于**： Outlook 
  
包含一条消息，在其中搜索过程中发现的文件夹的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PARENT_DISPLAY，PR_PARENT_DISPLAY_A，PR_PARENT_DISPLAY_W  <br/> |
|标识符：  <br/> |0x0E05  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>说明

对任何对象，这些属性不是。 它们仅可以显示搜索结果文件夹的内容表中。
  
这些属性和**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性不与每个其他相关。 他们所属完全不同的上下文。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

