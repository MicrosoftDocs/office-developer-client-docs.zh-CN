---
title: PidTagInstanceKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInstanceKey
api_type:
- HeaderDef
ms.assetid: 14fc5571-acc0-4d75-8598-964aee5ba01c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c237149c305a80012d1f06ea4373b892d25daec1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358509"
---
# <a name="pidtaginstancekey-canonical-property"></a>PidTagInstanceKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个值，该值唯一标识表格中的行。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_INSTANCE_KEY  <br/> |
|标识符:  <br/> |0x0FF6  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |表格  <br/> |
   
## <a name="remarks"></a>备注

此属性是一个二进制值，用于唯一标识表视图中的行。 在大多数表中，它是必填列。 如果一行包含在两个视图中，则有两个不同的实例键。 每次打开表时，行的实例键可能有所不同，但在表打开时仍保持不变。 使用表格时添加的行不会重复使用之前使用的实例键。 
  
使用 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性可关联扩展的所有行。 使用 **PR_INSTANCE_KEY** 在扩展中查找特定实例。 
  
在表中展开多值属性时，将针对每个扩展实例（即，针对该属性的每个值）创建一行。 每行对 **PR_INSTANCE_KEY** 具有唯一值，而所有其他列在整个扩展过程中保留其原始值。 
  
在表的分类排序中，可以将与实际数据不对应的行添加到排序结果中。 每个这样的行（如所有表中的所有行）都有其自己的唯一实例键。 
  
 **PR_INSTANCE_KEY** 表事件通知中也使用。 TABLE_NOTIFICATION结构的 **propIndex** 和 **propPrior** 成员是 [SPropValue](spropvalue.md)结构，它们 **PR_INSTANCE_KEY值。** [](table_notification.md) **propIndex** 成员指示已添加或已更改的行。 **propPrior** 成员指示行之前添加或更改的行 (PR_NULL表示第一行行) 。 
  
此值不会作为显示表的一部分进行复制。 
  
 **PR_INSTANCE_KEY** 是 [MAPIUID](mapiuid.md) 结构。 可以将所有实例键直接比较为二进制值。 
  
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
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

