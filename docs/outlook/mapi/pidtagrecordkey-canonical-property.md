---
title: PidTagRecordKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecordKey
api_type:
- COM
ms.assetid: a12fb9a2-799d-4112-b26c-4b2854c47cc2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd655c6245d25948d1dea1daace6a0644b47e378
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778182"
---
# <a name="pidtagrecordkey-canonical-property"></a>PidTagRecordKey 规范属性

  
  
**适用于**： Outlook 
  
包含特定对象的唯一的二进制相当标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECORD_KEY  <br/> |
|标识符：  <br/> |0x0FF9  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>说明

该属性从而便于查找引用对象，如内容表中查找其所在行。 此属性不能用于打开对象;使用此目的的项标识符。
  
附件子对象应唯一标识邮件中，此属性。 此标识符是保证保持不变后关闭并重新打开该邮件的唯一附件特征。 存储提供程序必须各个会话，以确保此保证保留此属性。
  
对于文件夹，此属性包含在文件夹层次结构表中使用的密钥。 通常，这是由**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性提供的相同的值。
  
对于邮件存储区，该属性等同于**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) 属性。
  
在消息存储对象中，此属性应是唯一的跨所有存储提供程序。 一种方法执行此操作是用[GUID](guid.md)结构或其他特有的特定邮件存储的值组合 （特有的提供程序类型） 的存储的**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性的值。 
  
此属性始终是可通过以下方法[IMAPIProp::SaveChanges](imapiprop-savechanges.md)第一次调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 某些提供程序可以使其可实例化后立即。 
  
客户端或服务提供程序可以将此属性的值进行比较使用 memcmp。 此方法不可行的条目标识符值。 但是，保证此属性是唯一的相同的消息存储中或通讯簿容器;从不同的容器的两个对象可以具有相同的此属性的值。
  
一个记录和搜索键之间的区别是记录密钥是特定于该对象，而搜索关键字可以复制到其他对象。 例如，两个对象的副本可以具有相同的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 值，但必须具有不同的值，此属性。
  
下表总结了**PR_ENTRYID**、 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 和此属性之间的重要不同之处。 
  
|**特征**|**PR_ENTRYID**|**PR_RECORD_KEY**|**PR_SEARCH_KEY**|
|:-----|:-----|:-----|:-----|
|Attachment 对象上所需  <br/> |否  <br/> |可访问  <br/> |否  <br/> |
|需要对文件夹对象  <br/> |可访问  <br/> |可访问  <br/> |否  <br/> |
|消息存储对象上所需  <br/> |可访问  <br/> |可访问  <br/> |否  <br/> |
|状态对象上所需  <br/> |可访问  <br/> |否  <br/> |否  <br/> |
|可创建由客户端  <br/> |否  <br/> |否  <br/> |可访问  <br/> |
|**SaveChanges**调用前可用 <br/> |也许  <br/> |也许  <br/> |邮件可能是其他人  <br/> |
|复制操作中发生的更改  <br/> |可访问  <br/> |可访问  <br/> |否  <br/> |
|可更改后副本的客户端  <br/> |否  <br/> |否  <br/> |可访问  <br/> |
|中的唯一...  <br/> |整个 world  <br/> |提供程序实例  <br/> |整个 world  <br/> |
|二进制 （与 memcmp) 相当  <br/> |否 — 使用**IMAPISupport:: CompareEntryIDs** <br/> |可访问  <br/> |可访问  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

