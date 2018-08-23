---
title: PidTagRowType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRowType
api_type:
- COM
ms.assetid: d57ce5c8-1f60-4709-b86a-4468c4208dfe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6e856cc8dc131c1b6266181a954a8da9cfb1d1ea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566101"
---
# <a name="pidtagrowtype-canonical-property"></a>PidTagRowType 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个值，指示的表中的行类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ROW_TYPE  <br/> |
|标识符：  <br/> |0x0FF5  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>注解

此属性仅在内容表上显示。 类别仅存在时，该项目。
  
此属性可以具有完全下列值之一：
  
TBL_LEAF_ROW 
  
> 代表实际数据，而不是类别行。
    
TBL_EMPTY_CATEGORY 
  
> 当前未使用。
    
TBL_EXPANDED_CATEGORY 
  
> 展开类别;用户界面通常显示此旁边其减号 （-）。
    
TBL_COLLAPSED_CATEGORY 
  
> 折叠类别;用户界面通常显示此它旁边的加号 （+）。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)
  
> 包含允许的操作的核心 table 对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagRowid 规范属性](pidtagrowid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

