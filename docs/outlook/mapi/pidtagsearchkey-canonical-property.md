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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345463"
---
# <a name="pidtagsearchkey-canonical-property"></a>PidTagSearchKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含标识搜索的相关对象的二进制比较键。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEARCH_KEY  <br/> |
|标识符:  <br/> |0x300B  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>备注

此属性提供相关对象（如邮件副本）的跟踪，并便于查找不需要的事件，如重复的收件人。
  
MAPI 使用特定规则来构造邮件收件人的搜索键。 搜索键通过连接地址类型 (（大写字符) 、冒号字符"："、规范形式的电子邮件地址和终止 null 字符）来形成。 此处的规范形式意味着正确大小写显示区分大小写的地址，不区分大小写的地址将转换为大写。 这一点对于保留邮件之间的关联很重要。
  
对于 message 对象，此属性可在创建邮件后立即通过 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法使用。 对于其他对象，在首次调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法后可用。 由于此属性是可更改的，因此在 **SaveChanges** 调用提交 [IMAPIProp：：SetProps](imapiprop-setprops.md)方法设置或更改的任何值之前，通过 **GetProps** 获取此属性是不可靠的。 
  
对于配置文件，MAPI 还提供名为 **MUID_PROFILE_INSTANCE** 的硬编码配置文件节，此属性用作其单个属性。 该密钥保证在以前创建的所有配置文件中是唯一的，并且比 **PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性更可靠，例如，可以使用相同的名称删除和重新创建该属性。
  
下表总结了 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 、PR_RECORD_KEY ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和此属性之间的重要差异。  
  
|**特征**|PR_ENTRYID****|PR_RECORD_KEY****|PR_SEARCH_KEY****|
|:-----|:-----|:-----|:-----|
|附件对象上必需  <br/> |否  <br/> |是  <br/> |否  <br/> |
|文件夹对象上必需  <br/> |是  <br/> |是  <br/> |否  <br/> |
|在邮件存储对象上是必需的  <br/> |是  <br/> |是  <br/> |否  <br/> |
|状态对象上必需  <br/> |是  <br/> |否  <br/> |否  <br/> |
|按客户端创建  <br/> |否  <br/> |否  <br/> |是  <br/> |
|在 **SaveChanges 之前可用** <br/> |取决于提供程序实现  <br/> |取决于提供程序实现  <br/> |对于邮件，是。 对于其他人，它依赖于提供程序实现。  <br/> |
|复制操作中已更改  <br/> |是  <br/> |是  <br/> |否  <br/> |
|复制后客户端可更改  <br/> |否  <br/> |否  <br/> |是  <br/> |
|在 ... 中是唯一的  <br/> |整个世界  <br/> |提供程序实例  <br/> |整个世界  <br/> |
|二进制 (与 memcmp)   <br/> |否 -- 使用 [IMAPISupport：：CompareEntryIDs](imapisupport-compareentryids.md) <br/> |是  <br/> |是  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagResponsibility 规范属性](pidtagresponsibility-canonical-property.md)
  
[PidTagStoreRecordKey 规范属性](pidtagstorerecordkey-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

