---
title: PidTagInReplyToId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInReplyToId
api_type:
- HeaderDef
ms.assetid: d435a65a-de01-4fb0-bc54-a87a2c4462ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f3ae69243da185430836903da9e7b0644c5db90
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594780"
---
# <a name="pidtaginreplytoid-canonical-property"></a>PidTagInReplyToId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含原始消息的**PR_INTERNET_MESSAGE_ID** ([PidTagInternetMessageId](pidtaginternetmessageid-canonical-property.md)) 属性值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IN_REPLY_TO_ID，PR_IN_REPLY_TO_ID_A，PR_IN_REPLY_TO_ID_W  <br/> |
|标识符：  <br/> |0x1042  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

必须在所有邮件答复设置这些属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagInternetMessageId 规范属性](pidtaginternetmessageid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

