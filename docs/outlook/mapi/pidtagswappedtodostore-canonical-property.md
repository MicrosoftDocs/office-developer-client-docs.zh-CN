---
title: PidTagSwappedToDoStore 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSwappedToDoStore
api_type:
- COM
ms.assetid: 1edae9ac-fc9a-4bfe-b053-99de848c5144
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 41aa97a52176cf68775d6fd507d3d042888092cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358903"
---
# <a name="pidtagswappedtodostore-canonical-property"></a>PidTagSwappedToDoStore 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定是否需要对电子邮件进行后传输处理。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SWAPPED_TODO_STORE  <br/> |
|标识符:  <br/> |0x0E2C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 非传输  <br/> |
   
## <a name="remarks"></a>注解

如果在草稿邮件上设置此属性, 则必须将其值设置为邮件的**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性的值。
  
有关详细信息, 请参阅[[OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)一节 "已标记邮件的传送后处理" 部分。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定用于电子邮件和其他对象提醒的属性和交互模型。
    
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

