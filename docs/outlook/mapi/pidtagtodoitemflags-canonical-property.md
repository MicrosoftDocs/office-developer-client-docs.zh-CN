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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400279"
---
# <a name="pidtagtodoitemflags-canonical-property"></a>PidTagToDoItemFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
代表一个待办事项已标记的条件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TODO_ITEM_FLAGS  <br/> |
|标识符：  <br/> |0x0E2B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>说明

此属性是在其中的每个位应设置为 1 如果关联的条件下表中应用，否则为 0 位字段。
  
||||
|:-----|:-----|:-----|
|数值  <br/> |名称  <br/> |说明  <br/> |
|不存在  <br/> |不适用  <br/> |未标记  <br/> |
|1  <br/> |todoTimeFlagged  <br/> |对象为标记的时间  <br/> |
|8  <br/> |todoRecipientFlagged  <br/> |只应在草稿 message 对象，设置和意味着对象进行了标记的收件人。  <br/> |
   
保留所有未指定表中的位。 它们必须被忽略，但如果已设置应保留。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
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

