---
title: PidTagSubjectPrefix 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubjectPrefix
api_type:
- COM
ms.assetid: 07fcb881-d873-45bf-b048-30f41d0d8d85
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8257c3c3583072d16e96e6ea9bba4632fc78f9ef
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385646"
---
# <a name="pidtagsubjectprefix-canonical-property"></a>PidTagSubjectPrefix 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含通常如指示上一条消息，某些操作的主题前缀"FW:"用于呼叫转移。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBJECT_PREFIX，PR_SUBJECT_PREFIX_A，PR_SUBJECT_PREFIX_W  <br/> |
|标识符：  <br/> |0x003D  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

建议对所有的消息对象都使用这些属性。 
  
主题前缀包括一个或多个字母数字字符后, 跟一个冒号和一个空格 （这是前缀的一部分）。 它必须包含冒号前的任何非字母数字字符。 通过为空字符串或未设置此属性，则可以表示前缀不存在。 
  
如果显式设置这些属性，字符串可以是任意长度和使用任何字母数字字符，但它必须匹配**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性开头的子字符串。 如果这些属性未设置发件人，并且必须计算，其内容的更多的限制。 计算前缀的规则是**PR_SUBJECT**必须开始使用一个、 两个或三个字母 (字母仅) 后跟一个冒号和一个空格。 如果**PR_SUBJECT**开头找到此类子字符串，则随后将成为这些属性的字符串 （及其还保持**PR_SUBJECT**开头）。 否则，这些属性保留未设置。 
  
这些属性和**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 应计算作为[IMAPIProp::SaveChanges](imapiprop-savechanges.md)实现的一部分。 客户端应不提示[IMAPIProp::GetProps](imapiprop-getprops.md)它们的值之前已经提交由**IMAPIProp::SaveChanges**呼叫。 
  
Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些 OLE **IStream**接口的义务。 客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回**MAPI_E_NOT_ENOUGH_MEMORY** 。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
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

