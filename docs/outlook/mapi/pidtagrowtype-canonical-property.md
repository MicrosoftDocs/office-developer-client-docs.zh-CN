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
ms.openlocfilehash: 962e8c92ae61e8b60862a3ae26a7cdfbf5034e89
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359512"
---
# <a name="pidtagrowtype-canonical-property"></a>PidTagRowType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个值，该值指示表格中行的类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ROW_TYPE  <br/> |
|标识符:  <br/> |0x0FF5  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 不可传输  <br/> |
   
## <a name="remarks"></a>备注

此属性只出现在内容表上。 类别仅在包含项目时存在。
  
此属性可以正好具有下列值之一：
  
TBL_LEAF_ROW 
  
> 表示实际数据，而不是分类行。
    
TBL_EMPTY_CATEGORY 
  
> 当前未使用。
    
TBL_EXPANDED_CATEGORY 
  
> 类别已展开;用户界面通常使用减号显示此 ( - ) 旁边。
    
TBL_COLLAPSED_CATEGORY 
  
> 折叠类别;用户界面通常会在旁边显示加 (+) 显示。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)
  
> 包括核心表对象的允许操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagRowid 规范属性](pidtagrowid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

