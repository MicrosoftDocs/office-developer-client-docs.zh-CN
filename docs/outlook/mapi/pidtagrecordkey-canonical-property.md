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
  
包含特定对象的唯一二进制比较标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECORD_KEY  <br/> |
|标识符:  <br/> |0x0FF9  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>备注

此属性便于查找对对象的引用，如在内容表中查找其行。 此属性不能用于打开对象;将条目标识符用于该目的。
  
附件子对象应在邮件中通过此属性进行唯一标识。 此标识符是唯一保证在关闭并重新打开邮件后保持不变的附件特征。 存储提供程序必须跨会话保留此属性以确保此保证。
  
对于文件夹，此属性包含文件夹层次结构表中使用的键。 通常，此值与[PidTagEntryId](pidtagentryid-canonical-property.md)  PR_ENTRYID (提供的值) 相同。
  
对于邮件存储，此属性与[PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md) PR_STORE_RECORD_KEY (属性) 相同。 
  
在邮件存储对象中，此属性在所有存储提供程序中应是唯一的。 实现此目标的方法之一是，将存储的 **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性值与提供程序类型) 所特有的 (属性值与 [GUID](guid.md) 结构或其他特定于特定邮件存储的值组合在一起。 
  
首次调用[IMAPIProp：：SaveChanges 方法后，此属性始终可以通过 IMAPIProp：：GetProps](imapiprop-savechanges.md)方法使用。 [](imapiprop-getprops.md) 某些提供程序可以在实例化后立即提供。 
  
客户端或服务提供商可以使用 memcmp 比较此属性的值。 条目标识符值不能这样做。 但是，此属性保证在同一邮件存储或通讯簿容器中是唯一的;不同容器中的两个对象可以具有相同的此属性的值。
  
记录和搜索键之间的一个区别是记录键特定于对象，而搜索键可以复制到其他对象。 例如，该对象的两个副本的[PidTagSearchKey PR_SEARCH_KEY (PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 值相同，但此属性必须具有不同的值。 
  
下表总结了 PidTagSearchKey PR_ENTRYID **、PR_SEARCH_KEY** **(** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 和此属性之间的重要差异。 
  
|**特征**|**PR_ENTRYID**|**PR_RECORD_KEY**|**PR_SEARCH_KEY**|
|:-----|:-----|:-----|:-----|
|附件对象上必需  <br/> |否  <br/> |是  <br/> |否  <br/> |
|文件夹对象上必需  <br/> |是  <br/> |是  <br/> |否  <br/> |
|在邮件存储对象上是必需的  <br/> |是  <br/> |是  <br/> |否  <br/> |
|状态对象上必需  <br/> |是  <br/> |否  <br/> |否  <br/> |
|按客户端创建  <br/> |否  <br/> |否  <br/> |是  <br/> |
|在调用 **SaveChanges 之前可用** <br/> |也许  <br/> |也许  <br/> |消息是其他可能  <br/> |
|复制操作中已更改  <br/> |是  <br/> |是  <br/> |否  <br/> |
|复制后客户端可更改  <br/> |否  <br/> |否  <br/> |是  <br/> |
|在 ... 中是唯一的  <br/> |整个世界  <br/> |提供程序实例  <br/> |整个世界  <br/> |
|二进制 (与 memcmp)   <br/> |否 -- 使用 **IMAPISupport：： CompareEntryIDs** <br/> |是  <br/> |是  <br/> |
   
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



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

