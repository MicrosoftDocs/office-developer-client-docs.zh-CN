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
ms.openlocfilehash: 05e29f01747e4d5aa2fe0b61e58fa2ba738a53fd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592848"
---
# <a name="pidtagoriginalauthorname-canonical-property"></a>PidTagOriginalAuthorName 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一条消息，即之前正在转发或答复邮件的第一个版本的作者的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_AUTHOR_NAME，PR_ORIGINAL_AUTHOR_NAME_A，PR_ORIGINAL_AUTHOR_NAME_W  <br/> |
|标识符：  <br/> |0x004D  <br/> |
|数据类型：  <br/> |PT_UNICODE PT_STRING8  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

这些属性是邮件的作者的地址属性的示例。 在首次提交邮件，客户端应用程序应为**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 的值来设置这些属性。 当转发或答复邮件永远不会更改它。
  
原始作者属性允许保留来自域外部的本地消息的信息。 当邮件到达从其他邮件的域时，如从 Internet，这些属性提供一种方法，以确保原始信息不会丢失。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDisplayName 规范属性](pidtagdisplayname-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

