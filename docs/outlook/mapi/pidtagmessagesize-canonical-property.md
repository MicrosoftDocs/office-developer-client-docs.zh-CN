---
title: PidTagMessageSize 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageSize
api_type:
- HeaderDef
ms.assetid: c67fb54b-8cc7-4fbc-8204-36fcddfa6192
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c52fd6d6caaec6f215856daead809ceb0bd76729
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574991"
---
# <a name="pidtagmessagesize-canonical-property"></a>PidTagMessageSize 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含消息对象上的所有属性的大小的总和，以字节为单位。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_SIZE  <br/> |
|标识符：  <br/> |0x0E08  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

建议消息对象公开此属性。 邮件大小表示的近似时该消息从一个消息存储库移至另一个被转移的字节数。 正在对消息对象的所有属性的大小的总和，它通常是相当大于单独的消息文本。 
  
大多数消息存储提供程序计算此属性的它们处理的邮件。 但是，某些消息存储提供程序不支持此属性。 在任何情况下，直到[IMAPIProp::SaveChanges](imapiprop-savechanges.md)或[IMessage::SubmitMessage](imessage-submitmessage.md)方法被调用此属性不可用。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹的操作。
    
[[MS OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)
  
> 指定允许的操作的核心消息存储对象。
    
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

