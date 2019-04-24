---
title: PidTagOriginalAuthorName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorNam
api_type:
- COM
ms.assetid: beb23742-d844-4d90-9b13-1ad376d4206c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bb62f3a44c9f17070db969683891fb2e2d62eb5e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355774"
---
# <a name="pidtagoriginalauthorname-canonical-property"></a>PidTagOriginalAuthorName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件的首个版本的作者的显示名称, 即邮件在转发或答复之前的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_AUTHOR_NAME、PR_ORIGINAL_AUTHOR_NAME_A、PR_ORIGINAL_AUTHOR_NAME_W  <br/> |
|标识符:  <br/> |0x004D  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

这些属性是邮件作者地址属性的示例。 首次提交邮件时, 客户端应用程序应将这些属性设置为**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 的值。 转发或答复邮件时, 它永远不会更改。
  
原始作者属性允许保留本地邮件域外部的信息。 当邮件到达其他邮件域 (例如从 Internet) 时, 这些属性提供了一种确保原始信息不会丢失的方法。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDisplayName 规范属性](pidtagdisplayname-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

