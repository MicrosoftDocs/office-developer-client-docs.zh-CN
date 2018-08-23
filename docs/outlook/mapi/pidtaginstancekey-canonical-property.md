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
ms.openlocfilehash: 53772fca5e8137dfd602d4c7d6f5e6ad40f9c50f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573430"
---
# <a name="pidtaginstancekey-canonical-property"></a>PidTagInstanceKey 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含唯一标识表中的行的值。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_INSTANCE_KEY  <br/> |
|标识符：  <br/> |0x0FF6  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Table  <br/> |
   
## <a name="remarks"></a>注解

此属性是唯一标识表视图中的行的二进制值。 它是大多数表中所需的列。 如果行包括在两个视图中，有两个不同的实例键。 行的实例项可能不同每次打开表时，但打开表时均保持不变。 行添加在使用表时不要重新使用以前使用的实例键。 
  
使用**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性用于关联的扩展的所有行。 使用**PR_INSTANCE_KEY**找到扩展中的特定实例。 
  
表格中展开一个多值的属性时, 创建行的扩展，每个实例，即为该属性的每个值。 每行时的其他所有列都保留整个扩展其原始值都为**PR_INSTANCE_KEY**属性的唯一值。 
  
在表的分类排序，可以为排序的结果添加不对应于实际数据的行。 每个这样的行，如所有表中的所有行都有其自己的唯一实例密钥。 
  
 **PR_INSTANCE_KEY**也可用于在表事件通知。 [TABLE_NOTIFICATION](table_notification.md)结构的**propIndex**和**propPrior**成员是[SPropValue](spropvalue.md)结构按住**PR_INSTANCE_KEY**值。 **PropIndex**成员指示已添加或更改的行。 **PropPrior**成员指示之前 （**PR_NULL**表示对第一行的更改） 的添加或更改行的行。 
  
显示表的一部分不复制此值。 
  
 **PR_INSTANCE_KEY**是一个[MAPIUID](mapiuid.md)结构。 可以直接将所有实例键都比较作为二进制值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
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

