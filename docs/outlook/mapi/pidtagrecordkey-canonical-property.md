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
ms.openlocfilehash: 7a3ae7db1fb97e97f7d0939b67f139af62477bf7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355263"
---
# <a name="pidtagrecordkey-canonical-property"></a>PidTagRecordKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含特定对象的唯一的二进制可比较标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECORD_KEY  <br/> |
|标识符:  <br/> |0x0FF9  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>注解

此属性有利于查找对某个对象的引用, 例如, 在内容表中查找其行。 此属性不能用于打开对象;为该目的使用条目标识符。
  
应通过此属性在邮件中唯一标识附件子属性。 此标识符是在关闭并重新打开邮件后, 保证其保持不变的唯一附件特征。 存储提供程序必须跨会话保留此属性, 以确保此保证。
  
对于文件夹, 此属性包含在文件夹层次结构表中使用的密钥。 通常情况下, 这与**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性提供的值相同。
  
对于邮件存储区, 此属性与**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) 属性相同。
  
在邮件存储对象中, 此属性在所有存储提供程序中应是唯一的。 执行此操作的一种方法是, 将**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性的值与特定邮件存储区的[GUID](guid.md)结构或其他值进行合并 (该提供程序类型唯一) 的值。 
  
在第一次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法后, 此属性始终可通过[IMAPIProp:: GetProps](imapiprop-getprops.md)方法使用。 某些提供程序可使其在实例化后立即可用。 
  
客户端或服务提供程序可以使用 memcmp 比较此属性中的值。 对于条目标识符值, 这是不可能的。 但是, 此属性在同一邮件存储或通讯簿容器中保证是唯一的;来自不同容器的两个对象可以具有该属性的相同值。
  
记录和搜索关键字之间的一种区别在于, 该记录键是特定于该对象的, 而搜索关键字可以复制到其他对象。 例如, 两个对象副本可以具有相同的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 值, 但必须具有此属性的不同值。
  
下表汇总了**PR_ENTRYID**、 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 和此属性之间的重要区别。 
  
|**特征**|**PR_ENTRYID**|**PR_RECORD_KEY**|**PR_SEARCH_KEY**|
|:-----|:-----|:-----|:-----|
|对附件对象是必需的  <br/> |否  <br/> |是  <br/> |否  <br/> |
|对 folder 对象是必需的  <br/> |是  <br/> |是  <br/> |否  <br/> |
|对邮件存储对象是必需的  <br/> |是  <br/> |是  <br/> |否  <br/> |
|对状态对象是必需的  <br/> |是  <br/> |否  <br/> |否  <br/> |
|可由客户端创建  <br/> |否  <br/> |否  <br/> |是  <br/> |
|在调用**SaveChanges**之前可用 <br/> |也  <br/> |也  <br/> |邮件是其他可能的  <br/> |
|在复制操作中更改  <br/> |是  <br/> |是  <br/> |否  <br/> |
|在复制后, 客户端可对其进行更改  <br/> |否  <br/> |否  <br/> |是  <br/> |
|中的唯一 .。。  <br/> |整个世界  <br/> |提供程序实例  <br/> |整个世界  <br/> |
|二进制可比较 (与 memcmp 一样)  <br/> |No--use **IMAPISupport:: CompareEntryIDs** <br/> |是  <br/> |是  <br/> |
   
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



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

