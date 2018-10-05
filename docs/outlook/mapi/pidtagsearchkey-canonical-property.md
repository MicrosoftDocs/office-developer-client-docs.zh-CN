---
title: PidTagSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: fcab369a-a1f4-4425-a272-e35046914a4d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e6b9ddf37c1db8ea28ae2f82caed2a487e551e5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389272"
---
# <a name="pidtagsearchkey-canonical-property"></a>PidTagSearchKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个标识用于搜索的相关的对象的二进制相当关键字。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEARCH_KEY  <br/> |
|标识符：  <br/> |0x300B  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>说明

此属性的相关对象，如邮件副本提供跟踪，从而便于查找不需要匹配项，如重复的收件人。
  
MAPI 的邮件的收件人，用于构建搜索关键字使用的特定规则。 搜索关键字通过将的地址类型 （在大写字符），而形成冒号 ':'，规范窗体和终止空字符中的电子邮件地址。 此处规范形式意味着区分大小写地址出现在正确的大小写，并且不区分大小写的地址转换为大写。 这是重要中保留邮件之间的关联。
  
对于邮件对象，该属性是可通过紧跟创建消息[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 对于其他对象，它位于关注[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法第一个呼叫。 此属性为可更改，因为它不可靠获取通过**GetProps**直到**SaveChanges**呼叫提交设置或更改[IMAPIProp::SetProps](imapiprop-setprops.md)方法的任何值。 
  
对于配置文件，MAPI 还提供此属性作为其单个属性名为**MUID_PROFILE_INSTANCE**，硬编码的配置文件一节。 此项保证创建过的所有配置文件中是唯一的并且可以比**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性，其中，例如，删除，并且具有相同名称重新创建更可靠。
  
下表总结了**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和此属性之间的重要不同之处。
  
|**特征**|PR_ENTRYID ***|PR_RECORD_KEY ***|PR_SEARCH_KEY ***|
|:-----|:-----|:-----|:-----|
|Attachment 对象上所需  <br/> |否  <br/> |是  <br/> |否  <br/> |
|需要对文件夹对象  <br/> |是  <br/> |是  <br/> |否  <br/> |
|消息存储对象上所需  <br/> |是  <br/> |是  <br/> |否  <br/> |
|状态对象上所需  <br/> |是  <br/> |否  <br/> |否  <br/> |
|可创建由客户端  <br/> |否  <br/> |否  <br/> |是  <br/> |
|**SaveChanges**前可用 <br/> |取决于提供程序实现  <br/> |取决于提供程序实现  <br/> |用于消息，是。 其他人，这取决于提供程序实现。  <br/> |
|复制操作中发生的更改  <br/> |是  <br/> |是  <br/> |否  <br/> |
|可更改后副本的客户端  <br/> |否  <br/> |否  <br/> |是  <br/> |
|中的唯一...  <br/> |整个 world  <br/> |提供程序实例  <br/> |整个 world  <br/> |
|二进制 （与 memcmp) 相当  <br/> |否 — 使用[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md) <br/> |是  <br/> |是  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagResponsibility 规范属性](pidtagresponsibility-canonical-property.md)
  
[PidTagStoreRecordKey 规范属性](pidtagstorerecordkey-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

