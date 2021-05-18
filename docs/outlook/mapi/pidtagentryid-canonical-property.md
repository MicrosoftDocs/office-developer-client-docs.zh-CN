---
title: PidTagEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagEntryId
api_type:
- HeaderDef
ms.assetid: ca02e873-c2d2-4d58-8df8-c05fbcdc8fba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: feb34cdbf8ba917936c3272bcaaf6eff040ddc3a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328586"
---
# <a name="pidtagentryid-canonical-property"></a>PidTagEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 MAPI 条目标识符，该标识符用于打开和编辑特定 MAPI 对象的属性。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ENTRYID  <br/> |
|标识符:  <br/> |0x0FFF  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>备注

此属性标识要实例化 **OpenEntry** 的对象，并通过 **相应的 IMAPIProp** 派生接口提供对它的所有属性的访问。 
  
此属性是所有邮件用户的基本地址属性之一。 
  
此属性可以包含长期标识符或短期标识符。 短期标识符更易于、更快地构造，但其范围和持续时间有限，通常仅限于当前会话和工作站。 它们通常用于临时性质的对象，如表行或对话框条目，然后放弃。 长期标识符用于具有更广泛和持久特性的对象。 
  
首次调用[IMAPIProp：：SaveChanges 方法后，此属性始终可以通过 IMAPIProp：：GetProps](imapiprop-savechanges.md)方法使用。 [](imapiprop-getprops.md) 一些服务提供商可以在实例化后立即提供。 提供程序必须始终从 **GetProps** 返回长期条目标识符。 因此，若要将短期标识符转换为长期标识符，只需打开 对象并通过 **GetProps** 获取其此属性。 
  
下表总结了此属性、PR_RECORD_KEY ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 之间的重要区别。  
  
|**特征**|**PR_ENTRYID**|**PR_RECORD_KEY**|**PR_SEARCH_KEY**|
|:-----|:-----|:-----|:-----|
|附件对象上必需  <br/> |否  <br/> |是  <br/> |否  <br/> |
|文件夹对象上必需  <br/> |是  <br/> |是  <br/> |否  <br/> |
|在邮件存储对象上是必需的  <br/> |是  <br/> |是  <br/> |否  <br/> |
|状态对象上必需  <br/> |是  <br/> |否  <br/> |否  <br/> |
|由客户端创建  <br/> |否  <br/> |否  <br/> |是  <br/> |
|在调用 **SaveChanges 之前可用** <br/> |取决于提供程序实现  <br/> |取决于提供程序实现  <br/> |对于邮件，是。 对于其他人，取决于提供程序实现。  <br/> |
|复制操作中已更改  <br/> |是  <br/> |是  <br/> |否  <br/> |
|复制后客户端可更改  <br/> |否  <br/> |否  <br/> |是  <br/> |
|内部唯一  <br/> |整个世界  <br/> |提供程序实例  <br/> |整个世界  <br/> |
|二进制 (与 memcmp)   <br/> |不使用 [IMAPISupport：： CompareEntryIDs](imapisupport-compareentryids.md) <br/> |是  <br/> |是  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端和服务器之间数据传输的顺序和流。
    
[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理对服务器上存储的文件夹权限列表的检索。
    
[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。
    
[[MS-OXWAVLS]](https://msdn.microsoft.com/library/69a276d8-5fc3-40ba-acd0-31cf42e6af58%28Office.15%29.aspx)
  
> 指定用于请求用户和资源的可用性信息的架构和方法。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStoreEntryId 规范属性](pidtagstoreentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

