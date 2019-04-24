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
  
包含二进制可比较的键, 用于标识搜索的相关对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEARCH_KEY  <br/> |
|标识符:  <br/> |0x300B  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>注解

此属性为相关对象 (如邮件副本) 提供跟踪, 便于查找不需要的事件, 如重复的收件人。
  
MAPI 使用特定的规则来构建邮件收件人的搜索键。 通过串联地址类型 (大写字符)、冒号字符 ":"、电子邮件地址规范格式以及终止 null 字符形成搜索关键字。 此处的规范表单表示区分大小写的地址以正确的大小写显示, 并且不区分大小写的地址将转换为大写。 这在保留邮件之间的相关性时非常重要。
  
对于 message 对象, 此属性通过[IMAPIProp:: GetProps](imapiprop-getprops.md)方法在邮件创建后立即可用。 对于其他对象, 在首次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法时, 将提供该对象。 由于此属性是可更改的, 在**SaveChanges**调用提交了由[IMAPIProp:: SetProps](imapiprop-setprops.md)方法设置或更改的任何值之前, 不能通过**GetProps**获取该属性。 
  
对于配置文件, MAPI 也提供名为**MUID_PROFILE_INSTANCE**的硬编码配置文件部分, 并将该属性作为其单个属性。 在创建的所有配置文件中, 此键都是唯一的, 并且可以比**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性更可靠, 例如, 可以使用相同的名称删除和重新创建该属性。
  
下表汇总了**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和此属性之间的重要区别。
  
|**特征**|PR_ENTRYID * * * *|PR_RECORD_KEY * * * *|PR_SEARCH_KEY * * * *|
|:-----|:-----|:-----|:-----|
|对附件对象是必需的  <br/> |否  <br/> |是  <br/> |否  <br/> |
|对 folder 对象是必需的  <br/> |是  <br/> |是  <br/> |否  <br/> |
|对邮件存储对象是必需的  <br/> |是  <br/> |是  <br/> |否  <br/> |
|对状态对象是必需的  <br/> |是  <br/> |否  <br/> |否  <br/> |
|可由客户端创建  <br/> |否  <br/> |否  <br/> |是  <br/> |
|在**SaveChanges**之前可用 <br/> |取决于提供程序实现  <br/> |取决于提供程序实现  <br/> |对于 "邮件", 是。 对于其他用户, 它取决于提供程序实现。  <br/> |
|在复制操作中更改  <br/> |是  <br/> |是  <br/> |否  <br/> |
|在复制后, 客户端可对其进行更改  <br/> |否  <br/> |否  <br/> |是  <br/> |
|中的唯一 .。。  <br/> |整个世界  <br/> |提供程序实例  <br/> |整个世界  <br/> |
|二进制可比较 (与 memcmp 一样)  <br/> |No--use [IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md) <br/> |是  <br/> |是  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagResponsibility 规范属性](pidtagresponsibility-canonical-property.md)
  
[PidTagStoreRecordKey 规范属性](pidtagstorerecordkey-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

