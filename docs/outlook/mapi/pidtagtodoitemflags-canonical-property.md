---
title: PidTagToDoItemFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagToDoItemFlags
api_type:
- COM
ms.assetid: bb7ccb45-ce08-4d22-9259-db15cd267e34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6ddc7231afef0a224b92be7fe86216e56200ab70
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284481"
---
# <a name="pidtagtodoitemflags-canonical-property"></a>PidTagToDoItemFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示To-Do标记的条件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TODO_ITEM_FLAGS  <br/> |
|标识符:  <br/> |0x0E2B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 不可传输  <br/> |
   
## <a name="remarks"></a>备注

此属性是位字段，如果下表中的关联条件适用，则每个位应设置为 1，否则为 0。
  
||||
|:-----|:-----|:-----|
|数值  <br/> |名称  <br/> |说明  <br/> |
|不存在  <br/> |不适用  <br/> |未标记  <br/> |
|1  <br/> |todoTimeFlagged  <br/> |对象已标记时间  <br/> |
|8   <br/> |todoRecipientFlagged  <br/> |应仅在草稿邮件对象上设置，这意味着对象已标记为收件人。  <br/> |
   
保留表中未指定的所有位。 必须忽略它们，但如果设置它们，应保留它们。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
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

