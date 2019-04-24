---
title: PidTagDepth 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDepth
api_type:
- HeaderDef
ms.assetid: 04d444a5-e97f-48e6-89a5-8a6cb2136408
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 75d390edd06aaf826f6b8c2d996e4e08bf6a7334
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360849"
---
# <a name="pidtagdepth-canonical-property"></a>PidTagDepth 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 integer 类型的值, 该值代表层次结构表中的对象的缩进或深度的相对级别。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEPTH  <br/> |
|标识符:  <br/> |0x3005  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 通用  <br/> |
   
## <a name="remarks"></a>注解

此属性还可以指定内容表中行的分类级别或层次结构中的层次结构深度表中的层次结构深度。 深度是从零开始的, 其中0表示最左边的类别。 在所有情况下, 属性值都代表相对值而不是绝对值。 例如, 在层次结构表中, 深度值相对于从中检索层次结构表的容器。 深度并不表示根容器的绝对深度。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)
  
> 包括核心表对象的允许操作。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagObjectType 规范属性](pidtagobjecttype-canonical-property.md)
  
[PidTagSelectable 规范属性](pidtagselectable-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

