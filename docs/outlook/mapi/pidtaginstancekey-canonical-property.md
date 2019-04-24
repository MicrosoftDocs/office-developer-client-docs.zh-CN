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
  
包含一个唯一标识表中的行的值。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_INSTANCE_KEY  <br/> |
|标识符:  <br/> |0x0FF6  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Table  <br/> |
   
## <a name="remarks"></a>注解

此属性是一个在表视图中唯一标识行的二进制值。 它是大多数表中的必需列。 如果两个视图中包含一个行, 则有两个不同的实例键。 每次打开表时, 行的实例键可能不同, 但在表打开时保持不变。 表在使用时添加的行不会重用以前使用的实例密钥。 
  
使用**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性关联展开的所有行。 使用**PR_INSTANCE_KEY**查找扩展中的特定实例。 
  
在表中展开多值属性时, 将为每个展开实例 (即该属性的每个值) 创建一行。 每个行都具有**PR_INSTANCE_KEY**属性的唯一值, 而所有其他列则在整个展开过程中保留其原始值。 
  
在已分类的表格中, 可以将不对应于实际数据的行添加到排序结果中。 与所有表中的所有行一样, 每个这样的行都有其自己唯一的实例键。 
  
 在表事件通知中也使用**PR_INSTANCE_KEY** 。 [TABLE_NOTIFICATION](table_notification.md)结构的**propIndex**和**propPrior**成员是保存**PR_INSTANCE_KEY**值的[SPropValue](spropvalue.md)结构。 **propIndex**成员指示已添加或更改的行。 **propPrior**成员指示在 "已添加" 或 "已更改" 行之前的行 (**PR_NULL**指示对第一行的更改)。 
  
此值不会作为显示表的一部分进行复制。 
  
 **PR_INSTANCE_KEY**是一种[MAPIUID](mapiuid.md)结构。 可以将所有实例键作为二进制值直接进行比较。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

